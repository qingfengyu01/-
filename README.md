POST&top_list_v2/update_score&device_id=XXX&game_mode=1&kill=1&length=35&market=apple&platform=1&push_channel=1&push_id=111111111222222223333333344444444&sid=XXX&uid=XXX&version=2.1


POST&top_list_v2/update_score&device_id=A0E0F5EB70764439A201ED1254778BAB2686000004478B7BE3F7&game_mode=1&kill=1000&length=5000&market=apple&platform=1&push_channel=1&push_id=111111111222222223333333344444444&sid=0448f8433731654c80a9ae47c24ad165&uid=02e055d049e54ddea55b73f54b9b577b&version=2.2

 private static void doSign(String url, HashMap<String, String> map) { String uri = url.substring(UrlConfig.K_API_URL.length()); ArrayList<String> pArray = new ArrayList(); for (Entry<String, String> entry : map.entrySet()) { pArray.add(((String) entry.getKey()) + "=" + ((String) entry.getValue())); } Collections.sort(pArray, new Comparator<String>() { public int compare(String lhs, String rhs) { return lhs.compareTo(rhs); } }); StringBuilder sb = new StringBuilder(); for (int i = 0; i < pArray.size(); i++) { if (i == 0) { sb.append((String) pArray.get(i)); } else { sb.append("&").append((String) pArray.get(i)); } } String pStr = sb.toString(); try { Log.i(TAG, "doSign: " + uri); map.put("snake_sign", SecurityUtil.hmacSHA1("POST&" + uri + "&" + pStr)); } catch (Exception e) { e.printStackTrace(); } }


![](/assets/屏幕快照 2016-09-09 15.07.06.png)
