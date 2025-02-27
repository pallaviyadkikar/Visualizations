
<html xml:lang="en" lang="en">
<head>
  <title>Microsoft Malware dataset Visualization </title>
  <style>
* { padding: 0; margin: 0; }
body {
  margin: 0 auto 0 auto;
  padding: 0;
  background-color: #33333f;
  width: 840px;
  font-family: "Avenir", "Avenir Next", Helvetica Neue, Arial;
  font-size: 0.95em;
}
a, a:visited { text-decoration: none; color: #7533f4; }
a:hover { text-decoration: underline; color: #f4b014; }
img, a.img, a:hover.img { border: none; }
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  max-width: 800px;
}
h1, h2, h3, h4, h5 {
  color: #492a7c;
  background-color: inherit;
  font-weight: normal;
  padding: 0 0 5px 0;
  margin: 15px 0 0 0;
  border: none;
  clear: right;
}
h1 { font-size: 18pt; margin:  5px 0 10px 0; line-height: 28px; }
h2 { font-size: 14pt; margin: 30px 0 15px 0; letter-spacing: 0.01em; border-bottom: 1px solid #ccc;  line-height: 20px;}
h3 { font-size: 13pt; }
h4 { font-size: 12pt; }
h5 { font-size: 11pt; }
p { margin: 0 0 10px 0; }
hr { border: 0px; border-top: 1px solid #ccc; height: 0px; }
ol { margin: 1em; }
.content {
  margin: 0;
  padding: 15px 20px;
  background-color: #ffffff;
}
.article {
  line-height: 1.5em;
}
.entry  {
  border-top: 1px solid #ddd;
  padding-top: 2px;
  margin-top: 3em;
}
  </style>
</head>

<body>
<div class='content'>

<section>
  <h1>Exploratory Data Analysis Of Dataset</h1>

  <p>
    <strong>Pallavi Yadkikar</strong>
  </p>
</section>

<section>
  <h2>Dataset</h2>


  <p>
    The data is available online at:
    <strong>
      <a href="https://arxiv.org/abs/1802.10135"></a>
    </strong>
  </p>
</section>

<section>
  <h2>Initial Analysis Questions</h2>
  <ol>
    <li>Which Microsoft product is most prone to malware attacks?</li>
    <li>Does installing antivirus products helps to prevent malware attacks?</li>
    <li>Do we need firewall or just Antivirus products are sufficient to prevent malware attacks?</li>
    <li> Does SmartScreen type plays any role in getting malware attacks?</li>
  </ol>
</section>

<section>
  <h2>Data Wrangling using pandas</h2>
  <div class="entry">
    <img src="V11.png" />
    <p class="caption">

    Before going into data exploration I felt, I need to find out which attributes contributes the most in a dataset. Therefore I used <b>python (pandas, matplotlib etc.) </b> to implement <b>Random Forest Algorithm for Feature Selection</b>. This algorithm calculates importance of each attribute in a dataset. So initially I had 85 attributes in dataset. After applying Random Forest Algorithm, I got 39 most important attributes. Then I used some pandas libraries to get top 13 features. The above image explains the top 39 features plotted against their importance scores.
    </p>
  </div>

  <div class="entry">
    <img src="V10.png" />
    <p class="caption">

    Above image explains how attributes are correlated to each other. It shows relationships between attributes which we can use for further expolaration.
    </p>
  </div>
</section>

<section>
  <h2>Discoveries &amp; Insights</h2>

  <div class="entry">
    <img src="V1.png" />
    <p class="caption">

    This visualizations shows which Microsoft Application versions are most vulnerable to Malware atatcks even if they are protected. Application version, color and size shows average of malware detections. The marks are labled by AppVersion. Data is filtered on IsProtected.
    </p>
  </div>

  <div class="entry">
    <img src="V2.png" />
    <p class="caption">

    The above image shows average of HasDetections for each product name. Color shows details about product name. The data is filtered on average of Firewall which keeps non Null vaules only.
    </p>
  </div>


  <div class="entry">
    <img src="V3.png" />
    <p class="caption">

    This describes average malware detection and average protection enabled for each Platform. Color shows details about Avg HasDetections & Avg IsProtected.
    </p>
  </div>

  <div class="entry">
    <img src="V4.png" />
    <p class="caption">

    As smartscreen was one of the important attribute I found out during data wrangling, I wanted to know in what ways SmartScreen is related to malware detection. Image shows Average of HasDetections for each Smart Screen. Color shows details about SmartScreen. The view is filtered on SmartScreen, which excludes Null values.
    </p>
  </div>

  <div class="entry">
    <img src="V5.png" />
    <p class="caption">

    Average of ScreenSize and average of HasDetections for each SmartScreen. The view is filtered on SmartScreen, which excludes Null values.From above image we can say that more the SmartScreen size is, more will be the malware atatcks.
    </p>
  </div>

  <div class="entry">
    <img src="V6.png" />
    <p class="caption">

    The image shows IsGamer and Has Detections for each Sku Edition.  Color shows details about  IsGamer and Has Detections. The view is filtered on Sku Edition, which excludes Invalid. If we exclude some outliers like Education edition, we can find out that being a gamer has a good chance of malware attack.
    </p>
  </div>

  <div class="entry">
    <img src="V7.png" />
    <p class="caption">

    Image shows that for sku edition, Installing Firewall doesnot really helps for malware attacks. This insight might be shocking because generally people feel that Firewall secure their system from possible malware attacks. Average of Firewall and average of HasDetections for each Platform is shown. The data is filtered on Microsoft Editions.
    </p>
  </div>

  <div class="entry">
    <img src="V8.png" />
    <p class="caption">

    Answer of above question is yes because, more the number of AntiVirus ProductStatesIdentifier, lesser will be the Malware Detections.The trends of average of AntiVirus ProductStatesIdentifier and average of HasDetections for number of AntiVirus Products Installed. The view is filtered on average of AntiVirusProductStatesIdentifier, which keeps non-Null values only.
    </p>
  </div>

  <div class="entry">
    <img src="V9.png" />
    <p class="caption">

    We know that windows8 platform had the most malware detection among all other microsoft platforms.So I further explored platform windows8. The trends of Avg. IsProtected and HasDetections for AntiVirus Products Installed broken down by Platform. Color shows details about Avg. IsProtected and HasDetections. The view is filtered on Platform and AntiVirus Products Installed.
    </p><p>From the above image, we cannot really say what causes Windows 8 to be most prone to malware attacks. Moreover, when maximum number of Antivirus products were installed, malware attacks were also highest. That means there might be a chance that, If we explore further with 5 Antivirus product in Windows 8 we might get some more rigid insights.
    </p>
  </div>

  <div class="entry">
    <img src="V12.png" />
    <p class="caption">
    	
	The plot of average of Has Detections for AV Products Installed broken down by Platform. The view is filtered on AV Products Installed, which keeps non-Null values only.
 </p>
 </div>

  <div class="entry">
    <h3>Summary</h3>
    <p>
    This  helped me to gain some rigid insights of my dataset. Pandas libraries are really helpful and fast while dealing with large dataset. I found out some really interesting facts and relationships which will help me further. In this dataset, attributes like IsProtected, SmartScreen, SmartScreenSize, AntiVirusProducts, Antivirus State Identifiers are most important for exploring HasDetections. Firewall shockingly does not provide much protections against malwares.
    </p>
  </div>
</section>




