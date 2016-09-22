POST&top_list_v2/update_score&device_id=XXX&game_mode=1&kill=1&length=35&market=apple&platform=1&push_channel=1&push_id=111111111222222223333333344444444&sid=XXX&uid=XXX&version=2.1

POST&top_list_v2/update_score&device_id=imei_865685027475153_uuid_147340653984592709&game_mode=1&kill=1&length=50&market=tencent&platform=2&push_channel=2&push_id=111111111222222223333333344444444&sid=7c239f35b712242a844e53671132b3c2&uid=4a064c76-59be-4c12-be37-73106f7d9caa&version=1.5.2


 private static void doSign(String url, HashMap<String, String> map) { String uri = url.substring(UrlConfig.K_API_URL.length()); ArrayList<String> pArray = new ArrayList(); for (Entry<String, String> entry : map.entrySet()) { pArray.add(((String) entry.getKey()) + "=" + ((String) entry.getValue())); } Collections.sort(pArray, new Comparator<String>() { public int compare(String lhs, String rhs) { return lhs.compareTo(rhs); } }); StringBuilder sb = new StringBuilder(); for (int i = 0; i < pArray.size(); i++) { if (i == 0) { sb.append((String) pArray.get(i)); } else { sb.append("&").append((String) pArray.get(i)); } } String pStr = sb.toString(); try { Log.i(TAG, "doSign: " + uri); map.put("snake_sign", SecurityUtil.hmacSHA1("POST&" + uri + "&" + pStr)); } catch (Exception e) { e.printStackTrace(); } }


![](/assets/屏幕快照 2016-09-09 15.07.06.png)






{"id":"1989","name":"\u4e13\u9898","english_name":"","sign":"zhuanti","pic":"","ui":"MixTypeTwo","attrs":{"showWeather":"0","listBackground":"#eeeeee","navBarTitle":"","navBarBackground":"#ffffff","openColumn":"0","showSlide":"0","slidePicCount":"5","slideHeight":"200","button_backgroundcolor":"#6496ff","shouldShowNavLogo":"0","shouldShowSlideTitle":"1","columnFontColor":"","columnCheckedBackgroundColor":"","columnSpace":"","columnBackgroundColorAlpha":"1","columnBackgroundColor":"","navigate_left_action":"","navigate_right_action":"","columnAverage":"0","columnStyle":"default","moduleIsLevel2":"0","sliderStyle":"0","columnLocalCity":"","showCoverColumn":"0","columnFontSize":"15","showfloatwindow":"","colomnUnchangeTitle":"0","slideImageHeightAsWidthRatio":"2","navigate_image_left":"","mixCardVerticalDistance":"0","slideTitleBold":"0","forceShowTitle":"0","moduleNavTitleColor":"#ffffff","openColumnSort":"0","canSubscribe":"0"},"api":{"column_url":"http:\/\/pmobile.ijntv.cn\/ijntv30\/zt_news_recomend_column.php","content_url":"http:\/\/pmobile.ijntv.cn\/ijntv30\/zt_news.php","detail_url":"http:\/\/pmobile.ijntv.cn\/ijntv30\/item.php","related_content_url":"http:\/\/pmobile.ijntv.cn\/ijntv30\/related_content.php","locate_column":"http:\/\/pmobile.ijntv.cn\/ijntv30\/locate_column.php","related_content":"http:\/\/pmobile.ijntv.cn\/ijntv30\/related_content.php","get_treasure":"http:\/\/pmobile.ijntv.cn\/ijntv30\/get_treasure.php"},"button_go":"","_listStyleSet":{"23":{"titleFontSize":"17","contentSideDistance":"5","contentTopDistance":"5","showBrief":"0","titleLineNum":"2"}}}

