<p style="text-indent:2em;">
	Download and install the SSH connection tool ：<a href="https://www.hostbuf.com/t/988.html">Finalshell</a> 
</p>
<p style="text-indent:2em;">
	Minimum VPS configuration requirements:Server;1-core,1G,10TB,Debian system
</p>
<p style="text-indent:2em;">
	First,update the Debian/Ubuntu system and install components.
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>allow port</strong> 
	</h1>
<a id="user-content-release-port" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#release-port"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>ufw allow 80    #Very important</code></pre>
</code></pre>
<pre class="notranslate"><code>ufw allow 443    #Very important</code></pre>
</code></pre>
<pre class="notranslate"><code>firewall-cmd --zone=public --add-port=Port number/tcp - Port number    #Release port1</code></pre>
</code></pre>
<pre class="notranslate"><code>iptables -A INPUT -p tcp --dport Port number -j ACCEPT    #Release port2</code></pre>
</code></pre>
<pre class="notranslate"><code>ufw allow Port number    #Release port3</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Turn off the firewall</strong> 
	</h1>
<a id="user-content-turn-off-the-firewall" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#turn-off-the-firewall"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>systemctl stop firewalld.service    #Turn off the firewall1</code></pre>
</code></pre>
<pre class="notranslate"><code>service iptables stop    #Turn off the firewall2</code></pre>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall3</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<hr />
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Midway deployment-build one-click script</strong> 
	</h1>
<a id="user-content-midway-deployment-build-one-click-script" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#midway-deployment-build-one-click-script"></a> 
</div>
<br />
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>Update the system</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system</code></pre>
</code></pre>
<pre class="notranslate"><code>yum install screen    #centos system</code></pre>
</code></pre>
<pre class="notranslate"><code>apt-get install wget    #wget system</code></pre>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	One-click installation script
</p>
</code></pre>
<pre class="notranslate"><code>wget -N --no-check-certificate href="https://github.com/ginuerzh/gost/releases/download/v2.11.0/gost-linux-amd64-2.11.0.gz gzip -d gost-linux-amd64-2.11.0.gz     #Deploy one-click script midway</code></pre>
</code></pre>
<pre class="notranslate"><code>wget --no-check-certificate -O gost.sh https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh && chmod +x gost.sh && ./gost.sh      #Deploy the final script code</code></pre>
<p style="text-indent:2em;">
	The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	mv gost-linux-amd64-2.11.0 gost    #Named gost
</p>
<p style="text-indent:2em;">
	chmod +x gost    #Add executable permissions to the gost file
</p>
<p style="text-indent:2em;">
	./gost -L udp://:38420 -L tcp://:38420 -F 
relay+tls://Terminal:33280 &gt;&gt; /dev/null 2&gt;&amp;1 &amp;    
	#IP address replacement
</p>
<p style="text-indent:2em;">
	./gost -L relay+tls://:8888/Terminal IP address replacement:443 &gt;&gt; /dev/null 2&gt;&amp;1 &amp;    
	#Terminal IP address replacement
</p>
</code></pre>
<pre class="notranslate"><code>./gost.sh       #Management script commands</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Transfer midway One-click installation of Nodepass panel 2026</strong> 
	</h1>
<a id="user-content-transfer-midway-one-click-installation-of-nodepass-panel-2026" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#transfer-midway-one-click-installation-of-nodepass-panel-2026"></a> 
</div>
<br />
<p style="text-indent:2em;">
	<strong>Preparation</strong>
</p>
<p style="text-indent:2em;">
	Prepare two VPSs: one for the intermediate server and one for the terminal server.
</p>
<p style="text-indent:2em;">
	Deploy the corresponding nodes on the terminal server in advance. Install the 3X-UI panel on the terminal server in advance.
</p>
<p style="text-indent:2em;">
	Set up domain name resolution for the intermediate server and the terminal server in advance.
</p>
<p style="text-indent:2em;">
	1、Apply for an ：<a href="https://github.com/slobys/SSL-Renewal">SSL certificate</a> 
</p>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)    #Deployment Commands</code></pre>
<p style="text-indent:2em;">
	2、Open Source Projects ：<a href="https://github.com/NodePassProject/npsh">Project</a>
</p>
<p style="text-indent:2em;">
	Nodepass Panel ：<a href="https://github.com/NodePassProject">Nodepass</a> 
</p>
<p style="text-indent:2em;">
	A. Main program installation [Mid-range and terminal installation]
</p>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>bash <(wget -qO- https://run.nodepass.eu/np.sh)    #Deployment Commands-1</code></pre>
</code></pre>
<pre class="notranslate"><code>bash <(curl -sSL https://run.nodepass.eu/np.sh)    #Deployment Commands-2</code></pre>
<p style="text-indent:2em;">
	B. Deploy Nodepass Panel [Mid-range terminal installation]
</p>
<p>
	<br />
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>bash <(wget -qO- https://run.nodepass.eu/dash.sh) install   #Deployment Commands-1</code></pre>
</code></pre>
<pre class="notranslate"><code>bash <(curl -sSL https://run.nodepass.eu/dash.sh) install   #Deployment Commands-2</code></pre>
<p style="text-indent:2em;">
	One-click installation script [ terminal installation selection]
</p>
<br />
<p style="text-indent:2em;">
	<strong>reset password</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>bash <(curl -sSL https://run.nodepass.eu/dash.sh) resetpwd    #reset password</code></pre>
<p>
	<br />
</p>	
<p style="text-indent:2em;">
	<strong>terminal installation selection</strong>
</p>
</code></pre>
<pre class="notranslate"><code>bash (curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)    #3X-UI installation panel</code></pre>
</code></pre>
<pre class="notranslate"><code>bash (wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)    #Sing-Box script</code></pre>
<p style="text-indent:2em;">
	4、The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Midway one-click installation of Aurora Panel 2026</strong> 
	</h1>
<a id="user-content-midway-one-click-installation-of-aurora-panel-2026" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#midway-one-click-installation-of-aurora-panel-2026"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system</code></pre>
<p style="text-indent:2em;">
	One-click installation panel
</p>
</code></pre>
<pre class="notranslate"><code>bash (curl -fsSL https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh)    #One-click installation of Aurora panel midway</code></pre>
<p style="text-indent:2em;">
	The router client replaces the transfer machine IP address and port
</p>
<p style="text-indent:2em;">
	<br />
</p>
<hr />
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Trojan Panel Installation Panel</strong> 
	</h1>
<a id="user-content-trojan-panel-installation-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#trojan-panel-installation-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>apt update -y     #Update the system</code></pre>
</code></pre>
<pre class="notranslate"><code>apt-get install ca-certificates wget -y update-ca-certificates   #Update the system's root certificate</code></pre>
</code></pre>
<pre class="notranslate"><code>wget -O tcp.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh" chmod +x tcp.sh; ./tcp.sh    #Enable BBR acceleration</code></pre>
</code></pre>
<pre class="notranslate"><code>source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install_script.sh)     #Trojan Panel Installation Panel</code></pre>
</code></pre>
<pre class="notranslate"><code>source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install_script_standalone.sh)     #Trojan Panel Installation Panel</code></pre>
<p style="text-indent:2em;">
</p>
<p style="text-indent:2em;">
	Default login account: sysadmin Default login password: 123456
</p>
<p style="text-indent:2em;">
	Recommended installation order: Trojan Panel Backend &gt; Trojan Panel Frontend -&gt; Trojan Panel Cor
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>One-click installation of Sing-Box panel</strong> 
	</h1>
<a id="user-content-one-click-installation-of-sing-box-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#one-click-installation-of-sing-box-panel"></a> 
</div>
	<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system</code></pre>
</code></pre>
<pre class="notranslate"><code>bash (curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)      #Apply for an SSL certificate with one click</code></pre>
<p style="text-indent:2em;">
	One-click installation panel
</p>
</code></pre>
<pre class="notranslate"><code>bash (curl -Ls https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh)      #One-click installation of Sing-Box and Xray panels</code></pre>
<p style="text-indent:2em;">
</p>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>sb one-click deployment builds sing-box script</strong> 
	</h1>
<a id="user-content-sb-one-click-deployment-builds-sing-box-script" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#sb-one-click-deployment-builds-sing-box-script"></a>
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>sudo ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)     #sb one-key script</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Hysteria 2 One-Click Script Deployment</strong> 
	</h1>
<a id="user-content-sb-one-click-deployment-builds-sing-box-script" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#sb-one-click-deployment-builds-ysteria2-script"></a>
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong> 
</p>
</code></pre>
<pre class="notranslate"><code>sudo ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y    #Update system</code></pre>
<p style="text-indent:2em;">
	hysteria2 executes the dependency installation (please execute the dependency installation once before running the installation script)
</p>
</code></pre>
<pre class="notranslate"><code>wget -O phy2.sh https://raw.githubusercontent.com/seagullz4/hysteria2/main/phy2.sh && chmod +x phy2.sh && bash phy2.sh    #Hysteria2 installation dependencies</code></pre>
<p style="text-indent:2em;">
	Hysteria2 One-Click Deployment Script
</p>
</code></pre>
<pre class="notranslate"><code>bash <(curl -Lso- https://raw.githubusercontent.com/GeorgianaBlake/Hysteria2/refs/heads/main/install.sh)    #Hysteria2 One-Click Deployment Script</code></pre>
<p style="text-indent:2em;">
	Hysteria2 Shell Version One-Click Script
</p>
</code></pre>
<pre class="notranslate"><code>wget -N --no-check-certificate https://raw.githubusercontent.com/flame1ce/hysteria2-install/main/hysteria2-install-main/hy2/hysteria.sh && bash hysteria.sh    #Hysteria2 Shell Version One-Click Script</code></pre>
<p style="text-indent:2em;">
	Hysteria2 Pure Version One-Click Script
</p>
</code></pre>
<pre class="notranslate"><code>wget -O hy2.py https://raw.githubusercontent.com/seagullz4/hysteria2/main/hysteria2.py && chmod +x hy2.py && python3 hy2.py    #Hysteria2 Pure Version One-Click Script</code></pre>
<p style="text-indent:2em;">
	project hysteria2：<a href="https://github.com/seagullz4/hysteria2">project hysteria2</a> 
</p>
<p style="text-indent:2em;">
	open source projects hysteria2 ：<a href="https://github.com/GeorgianaBlake/Hysteria2">open source projects hysteria2</a> 
</p>
<p style="text-indent:2em;">
<br />
</p>
<hr />
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Install x-ui-yg panel</strong> 
	</h1>
<a id="user-content-install-x-ui-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#install-x-ui-yg-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
</p>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y    #Update system</code></pre>
</code></pre>
<pre class="notranslate"><code>bash <(wget -qO- https://raw.githubusercontent.com/yonggekkk/x-ui-yg/main/install.sh)    #Install x-ui-yg panel</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Install x-ui panel</strong> 
	</h1>
<a id="user-content-install-x-ui-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#install-x-ui-panel"></a> 
</div>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
<p style="text-indent:2em;">
</p>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>bash (curl -Ls href="https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)    #Install x-ui panel</code></pre>
<p style="text-indent:2em;">
	<br />
</p>
<div class="markdown-heading">
	<h1 class="heading-element">
		<strong>Install 3x-ui panel</strong> 
	</h1>
<a id="user-content-install-3x-ui-panel" class="anchor" href="https://github.com/linsiqun/VSP-node-deployment#install-3x-ui-panel"></a> 
</div>
<p style="text-indent:2em;">
	3X-UI open source project ：<a href="https://github.com/MHSanaei/3x-ui">address</a> 
</p>
<p style="text-indent:2em;">
	<strong>The following command</strong>
</p>
</code></pre>
<pre class="notranslate"><code>ufw disable    #Turn off the firewall</code></pre>
</code></pre>
<pre class="notranslate"><code>apt update -y &amp;&amp; apt install curl sudo wget git -y    #Debian/Ubuntu system</code></pre>
<p style="text-indent:2em;">
	One-click installation panel
</p>
</code></pre>
<pre class="notranslate"><code>bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)    #3x-ui panel</code></pre>
<br />
<ol>
	<li>
		<p>
			Apply for an SSL certificate (disable the firewall (sudo 
ufw disable)/allow access to port 80 (ufw allow 80) for the certificate 
application to succeed).
		</p>
	</li>
	<li>
		<p>
			Configure the node (Important: If the node cannot access the internet, remember to allow access to the node port.)
		</p>
	</li>
</ol>
	<br />
<p style="text-indent:2em;">
	①vless+grpc+reality  80
</p>
<p style="text-indent:2em;">
	②vless+tcp+reality
</p>
<p style="text-indent:2em;">
	②vless+xhttp+reality
</p>
<p style="text-indent:2em;">
	③vless+ws+tls  443
</p>
<p style="text-indent:2em;">
	④vless+tcp+tls
<p style="text-indent:2em;">
	<br />
<pre><span class="pl-c"><span class="pl-c">Server deployment complete, Enable BBR</span></span></pre>
</p>
</p>
