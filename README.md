# ymtz-zyfw-ndxs
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>分娩镇痛医保政策查询</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: "PingFang SC", "Microsoft YaHei", "Helvetica Neue", sans-serif;
    min-height: 100vh;
    background: linear-gradient(160deg, #fff5f5 0%, #fde8e8 35%, #fbd5d5 70%, #f8caca 100%);
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 60px 20px 80px;
    position: relative;
    overflow-x: hidden;
  }

  /* 漂浮装饰 */
  .bg-deco {
    position: fixed;
    border-radius: 50%;
    pointer-events: none;
    z-index: 0;
  }
  .deco-1 {
    top: -100px; right: -80px;
    width: 360px; height: 360px;
    background: radial-gradient(circle, rgba(192,57,43,0.10) 0%, transparent 70%);
  }
  .deco-2 {
    bottom: -120px; left: -100px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(192,57,43,0.08) 0%, transparent 70%);
  }
  .deco-3 {
    top: 40%; left: 5%;
    width: 80px; height: 80px;
    background: radial-gradient(circle, rgba(255,255,255,0.5) 0%, transparent 70%);
  }
  .deco-4 {
    top: 20%; right: 8%;
    width: 60px; height: 60px;
    background: radial-gradient(circle, rgba(255,255,255,0.4) 0%, transparent 70%);
  }

  /* 漂浮小星点 */
  .star {
    position: fixed;
    width: 6px; height: 6px;
    background: rgba(192,57,43,0.15);
    border-radius: 50%;
    pointer-events: none;
    z-index: 0;
    animation: floatStar 6s ease-in-out infinite;
  }
  .star:nth-child(5) { top: 15%; left: 12%; animation-delay: 0s; }
  .star:nth-child(6) { top: 70%; left: 85%; animation-delay: 1.5s; }
  .star:nth-child(7) { top: 45%; left: 90%; animation-delay: 3s; }
  .star:nth-child(8) { top: 80%; left: 20%; animation-delay: 4.5s; }

  @keyframes floatStar {
    0%, 100% { transform: translateY(0) scale(1); opacity: 0.4; }
    50% { transform: translateY(-12px) scale(1.3); opacity: 0.8; }
  }

  .container {
    position: relative;
    z-index: 1;
    width: 100%;
    max-width: 720px;
  }

  /* 标题区 */
  .header {
    text-align: center;
    margin-bottom: 40px;
    animation: fadeInDown 0.8s ease;
  }

  @keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .header .icon-wrap {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 64px; height: 64px;
    background: linear-gradient(135deg, #ffffff, #fde8e8);
    border-radius: 50%;
    box-shadow: 0 6px 20px rgba(192,57,43,0.12);
    margin-bottom: 14px;
    font-size: 30px;
  }

  .header h1 {
    font-size: 28px;
    font-weight: 700;
    color: #a93226;
    letter-spacing: 1.5px;
    margin-bottom: 10px;
  }

  .header .divider {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin-bottom: 10px;
  }

  .header .divider span {
    display: block;
    width: 30px; height: 2px;
    background: linear-gradient(90deg, transparent, #e8b4b4, transparent);
  }

  .header .divider i {
    font-style: normal;
    font-size: 12px;
    color: #d98a8a;
    letter-spacing: 2px;
  }

  .header p {
    font-size: 14px;
    color: #b07a7a;
    letter-spacing: 0.5px;
  }

  /* 搜索框 */
  .search-box {
    background: rgba(255, 255, 255, 0.92);
    backdrop-filter: blur(10px);
    border-radius: 22px;
    padding: 28px 26px;
    box-shadow: 0 10px 40px rgba(192,57,43,0.10), 0 2px 10px rgba(192,57,43,0.06);
    display: flex;
    gap: 12px;
    align-items: center;
    flex-wrap: wrap;
    justify-content: center;
    border: 1px solid rgba(255,255,255,0.8);
    animation: fadeInUp 0.8s ease 0.15s both;
  }

  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .search-box input {
    flex: 1;
    min-width: 200px;
    padding: 15px 22px;
    font-size: 16px;
    border: 2px solid #f0d0d0;
    border-radius: 16px;
    outline: none;
    transition: all 0.3s ease;
    background: #fffafa;
    color: #333;
  }

  .search-box input:focus {
    border-color: #c0392b;
    background: #ffffff;
    box-shadow: 0 0 0 4px rgba(192,57,43,0.08);
    transform: translateY(-1px);
  }

  .search-box input::placeholder { color: #c9a9a9; }

  .search-box button {
    padding: 15px 36px;
    font-size: 16px;
    font-weight: 600;
    background: linear-gradient(135deg, #d94a3a, #a93226);
    color: #fff;
    border: none;
    border-radius: 16px;
    cursor: pointer;
    transition: all 0.25s ease;
    letter-spacing: 3px;
    box-shadow: 0 6px 18px rgba(192,57,43,0.30);
    position: relative;
    overflow: hidden;
  }

  .search-box button::after {
    content: "";
    position: absolute;
    top: 0; left: -100%;
    width: 100%; height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
    transition: left 0.5s ease;
  }

  .search-box button:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(192,57,43,0.40);
  }

  .search-box button:hover::after { left: 100%; }

  .search-box button:active { transform: translateY(0); }

  /* 结果区 */
  #result { margin-top: 30px; }

  .result-header {
    font-size: 17px;
    font-weight: 700;
    color: #a93226;
    margin-bottom: 6px;
    padding-left: 6px;
    animation: fadeInUp 0.5s ease;
  }

  .result-sub {
    font-size: 13px;
    color: #b07a7a;
    margin-bottom: 18px;
    padding-left: 6px;
    animation: fadeInUp 0.5s ease;
  }

  .option-card {
    background: rgba(255,255,255,0.95);
    border-radius: 18px;
    padding: 20px 24px;
    margin-bottom: 14px;
    box-shadow: 0 4px 18px rgba(192,57,43,0.07);
    border-left: 5px solid #e8b4b4;
    transition: all 0.3s ease;
    cursor: pointer;
    animation: cardIn 0.5s ease both;
    position: relative;
    overflow: hidden;
  }

  .option-card::before {
    content: "";
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: linear-gradient(90deg, rgba(192,57,43,0.03), transparent);
    opacity: 0;
    transition: opacity 0.3s ease;
  }

  .option-card:hover::before { opacity: 1; }

  .option-card:hover {
    transform: translateX(8px);
    border-left-color: #c0392b;
    box-shadow: 0 8px 28px rgba(192,57,43,0.16);
  }

  .option-card a {
    color: #a93226;
    font-weight: 700;
    font-size: 15px;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 8px;
    position: relative;
    z-index: 1;
  }

  .option-card a::before {
    content: "📌";
    font-size: 13px;
    opacity: 0.7;
  }

  .option-card a::after {
    content: "→";
    font-size: 14px;
    margin-left: auto;
    transition: transform 0.25s ease;
  }

  .option-card:hover a::after { transform: translateX(5px); }

  .option-card p {
    font-size: 13px;
    color: #8a6a6a;
    margin-top: 10px;
    line-height: 1.7;
    padding-left: 22px;
    position: relative;
    z-index: 1;
  }

  /* 卡片依次淡入 */
  .option-card:nth-child(1) { animation-delay: 0.05s; }
  .option-card:nth-child(2) { animation-delay: 0.12s; }
  .option-card:nth-child(3) { animation-delay: 0.19s; }
  .option-card:nth-child(4) { animation-delay: 0.26s; }
  .option-card:nth-child(5) { animation-delay: 0.33s; }

  @keyframes cardIn {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* 空状态 */
  .empty-tip {
    text-align: center;
    padding: 50px 20px;
    color: #b07a7a;
    font-size: 14px;
    line-height: 1.9;
    background: rgba(255,255,255,0.7);
    border-radius: 18px;
    animation: fadeInUp 0.5s ease;
  }

  .empty-tip .emoji {
    font-size: 36px;
    display: block;
    margin-bottom: 12px;
  }

  .empty-tip .available {
    margin-top: 14px;
    font-size: 13px;
    color: #a93226;
    font-weight: 600;
    line-height: 2;
  }

  /* 底部 */
  .footer {
    margin-top: 60px;
    text-align: center;
    font-size: 12px;
    color: #c9a9a9;
    line-height: 2;
    animation: fadeInUp 0.8s ease 0.4s both;
  }

  .footer .line {
    display: block;
    width: 40px; height: 1px;
    background: #e8c8c8;
    margin: 0 auto 12px;
  }

  /* 移动端 */
  @media (max-width: 520px) {
    body { padding: 36px 14px 60px; }
    .header h1 { font-size: 22px; }
    .header .icon-wrap { width: 54px; height: 54px; font-size: 26px; }
    .search-box { padding: 20px 16px; flex-direction: column; border-radius: 18px; }
    .search-box input { width: 100%; }
    .search-box button { width: 100%; }
    .option-card { padding: 16px 18px; }
    .option-card p { padding-left: 0; }
  }
</style>
</head>
<body>

<!-- 装饰 -->
<div class="bg-deco deco-1"></div>
<div class="bg-deco deco-2"></div>
<div class="bg-deco deco-3"></div>
<div class="bg-deco deco-4"></div>
<div class="star"></div>
<div class="star"></div>
<div class="star"></div>
<div class="star"></div>

<div class="container">

  <div class="header">
    <div class="icon-wrap">🤱</div>
    <h1>分娩镇痛医保政策查询</h1>
    <div class="divider">
      <span></span>
      <i>医娩同舟</i>
      <span></span>
    </div>
    <p>输入浙江省内地区名称，一键直达官方政策页面</p>
  </div>

  <div class="search-box">
    <input type="text" id="regionInput" placeholder="请输入地区名称，如：杭州市" onkeydown="if(event.key==='Enter')searchPolicy()">
    <button onclick="searchPolicy()">查 询</button>
  </div>

  <div id="result"></div>

  <div class="footer">
    <span class="line"></span>
    数据来源：浙江省及各地市医保局官方公开信息<br>
    医娩同舟 · 分娩镇痛全周期服务团队
  </div>

</div>

<script>
var policyData = {
  "浙江省": {
    "options": [
      {
        "name": "浙江省医保局（分娩镇痛纳入支付范围通知·2022）",
        "url": "http://ybj.zj.gov.cn/art/2022/6/30/art_1229113757_2409744.html",
        "summary": "首次将分娩镇痛纳入基本医疗保险支付范围，自2022年7月1日起施行"
      },
      {
        "name": "浙江省医保局（椎管内麻醉价格政策·2022）",
        "url": "http://ybj.zj.gov.cn/art/2022/11/17/art_1229113757_2447698.html",
        "summary": "分娩镇痛按椎管内麻醉收费，405元/2小时，超时加收140元/小时，甲类支付"
      },
      {
        "name": "浙江省医保局（生育支持政策解读·2025）",
        "url": "http://ybj.zj.gov.cn/art/2025/12/5/art_1229667819_2582250.html",
        "summary": "分娩镇痛硬膜外套件、镇痛装置纳入甲类支付；生育服务包自然分娩6200元，2025年12月1日起执行"
      },
      {
        "name": "浙江省医保局（分娩镇痛项目编码·2025）",
        "url": "http://ybj.zj.gov.cn/art/2025/11/4/art_1229225623_2578740.html",
        "summary": "公布分娩镇痛项目编码013112020090000及超时加收编码"
      },
      {
        "name": "浙大妇院（分娩镇痛科普介绍）",
        "url": "https://www.womanhospital.cn//list/4c155217c3794ffab94836ee94241ab2/30f758f8bb15485c9b4ceb9cfae84979.html",
        "summary": "硬膜外麻醉镇痛的安全性与常见副作用说明，医院自2009年起24小时提供"
      }
    ]
  },
  "杭州市": {
    "options": [
      {
        "name": "杭州市医保局（产科价格项目通知）",
        "url": "https://zjjcmspublicnew.oss-cn-hangzhou-zwynet-d01-a.internet.cloud.zj.gov.cn/cms_files/filemanager/48758/attach/20259/7C253F77AAB7E66045BC429FE2E39F93.docx",
        "summary": "自然分娩限额6200元，分娩镇痛耗材按甲类支付，省内直接刷卡"
      },
      {
        "name": "杭州市医保局（局长专访·五个全）",
        "url": "https://hznews.hangzhou.com.cn/kejiao/content/2026-02/04/content_9173124.htm",
        "summary": "全人群覆盖、全周期保障，分娩镇痛纳入保障，人均减负5000元以上"
      },
      {
        "name": "萧山日报（生育保障政策热点解答）",
        "url": "https://xsrb.xsnet.cn/html/2026-03/18/content_79495_19374621.htm",
        "summary": "杭州参保孕产妇享全额保障，分娩镇痛全额纳入，省内直接结算"
      }
    ]
  },
  "宁波市": {
    "options": [
      {
        "name": "宁波市第一医院（分娩镇痛价格公示）",
        "url": "http://www.nbdyyy.com/art/2025/10/16/art_16334_642321.html",
        "summary": "分娩镇痛203元/小时，按甬医保发〔2025〕24号执行"
      },
      {
        "name": "鄞州新闻网（2000余人享零自付）",
        "url": "https://www.nbyznews.cn/ldnews/202604/t20260401_7193579.shtml",
        "summary": "生育服务包含分娩镇痛，无需额外付费，累计报销超360万元"
      }
    ]
  },
  "温州市": {
    "options": [
      {
        "name": "温州市医保局（生育服务包惠及温州孕妇）",
        "url": "https://ybj.wenzhou.gov.cn/col/col1659509/art/2026/art_2970349e1a694790bd86986a12e1a9d2.html",
        "summary": "自然分娩限额6200元，产前检查3450元，分娩镇痛耗材按甲类支付"
      },
      {
        "name": "温州市医保局（2025年价格表）",
        "url": "http://www.yqrmyy.com/upload/file/2025-10/1760408171104639.docx",
        "summary": "分娩镇痛按203元/小时，超2小时加收140元/小时，医保甲类"
      }
    ]
  },
  "绍兴市": {
    "options": [
      {
        "name": "绍兴网（宝妈多报销6500元）",
        "url": "https://www.shaoxing.com.cn/p/3431912.html",
        "summary": "分娩镇痛不用额外加钱，自然分娩一孩最高保障9995元，已惠及1.96万人"
      },
      {
        "name": "绍兴文明网（新生育服务包全面减负）",
        "url": "http://zjsx.wenming.cn/jwmsxf/202602/t20260202_9154272.html",
        "summary": "越城区自2025年12月1日起实施，分娩镇痛纳入医保支付范围"
      }
    ]
  },
  "嘉兴市": {
    "options": [
      {
        "name": "嘉兴市医保局（分娩镇痛纳入医保报销）",
        "url": "https://ybj.jiaxing.gov.cn/art/2022/12/1/art_1229493454_58920303.html",
        "summary": "自然分娩过程中分娩镇痛按椎管内麻醉收费，费用下降约85%"
      }
    ]
  },
  "湖州市": {
    "options": [
      {
        "name": "湖州市人民政府（生育服务包减免近2000万）",
        "url": "https://m.163.com/dy/article/KO9MN7AQ05568W0A.html",
        "summary": "分娩镇痛纳入生育服务包，已累计减免近2000万元"
      }
    ]
  },
  "金华市": {
    "options": [
      {
        "name": "金华新闻网（生育服务包落地见效）",
        "url": "https://www.jhnews.com.cn/xw/1864002",
        "summary": "分娩镇痛耗材纳入医保，服务包覆盖产前到产后"
      }
    ]
  },
  "衢州市": {
    "options": [
      {
        "name": "衢州晚报（无痛分娩纳入医保报道）",
        "url": "http://qzwb.qz828.com/html/2022-12/06/content_3396_7062153.htm",
        "summary": "分娩镇痛按椎管内麻醉收费，405元/2小时，自2022年12月1日起执行"
      }
    ]
  },
  "舟山市": {
    "options": [
      {
        "name": "舟山市医保局（全市2409人享受）",
        "url": "http://zsyb.zhoushan.gov.cn/col/col1642140/art/2026/art_b78fa9284128457ea23104bd34812416.html",
        "summary": "分娩镇痛耗材纳入甲类支付，累计报销303.88万元"
      }
    ]
  },
  "台州市": {
    "options": [
      {
        "name": "台州市医保局（生育服务包新闻发布会）",
        "url": "https://ylbzj.zjtz.gov.cn/col/col1229576028/art/2026/art_ef875590a0d3965c4926c0a2f575226f.html",
        "summary": "自然分娩服务包含分娩镇痛，限额6200元，难产加1000元"
      },
      {
        "name": "台州市中心医院（分娩镇痛纳入医保报销）",
        "url": "http://tzzxyy.zwjk.com/ksdh/wk/fck/fck-ksdt/content_8497",
        "summary": "分娩镇痛按椎管内麻醉收费，职工医保支付80%，产妇个人支付81元"
      }
    ]
  },
  "丽水市": {
    "options": [
      {
        "name": "丽水市医保局（浙江省生育服务包政策落地）",
        "url": "http://ybj.lishui.gov.cn",
        "summary": "执行省级统一政策，分娩镇痛耗材按甲类支付"
      }
    ]
  }
};

function searchPolicy() {
  var input = document.getElementById("regionInput").value.trim();
  var resultDiv = document.getElementById("result");
  if (!input) { resultDiv.innerHTML = "<div class='empty-tip'><span class='emoji'>💡</span>请输入地区名称，如：杭州市、温州市</div>"; return; }
  var matched = null;
  for (var k in policyData) { if (k.indexOf(input) !== -1 || input.indexOf(k) !== -1) { matched = k; break; } }
  if (matched) {
    var data = policyData[matched];
    var html = "<div class='result-header'>已找到：" + matched + "</div>";
    html += "<div class='result-sub'>请选择要查看的官方页面：</div>";
    data.options.forEach(function(opt) {
      html += "<div class='option-card'>";
      html += "<a href='" + opt.url + "' target='_blank'>" + opt.name + "</a>";
      html += "<p>" + opt.summary + "</p>";
      html += "</div>";
    });
    resultDiv.innerHTML = html;
  } else {
    resultDiv.innerHTML = "<div class='empty-tip'><span class='emoji'>🔍</span>暂未收录该地区<br><span class='available'>可查询：浙江省、杭州市、宁波市、温州市、绍兴市、嘉兴市、湖州市、金华市、衢州市、舟山市、台州市、丽水市</span></div>";
  }
}
</script>
</body>
</html>
