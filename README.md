# WebGIS
各种基于WebGIS的Demo系统


# OpenLayers加载百度地图
参考地址：https://blog.csdn.net/qingyafan/article/details/49403989

# Leaflet加载百度地图

# Asp.net Core部署到Linux Nginx环境下配置
https://docs.microsoft.com/zh-cn/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-2.2

# 部署到Linux后的问题
1.程序可以正常运行，但是wwwroot里面的静态资源都不能访问。
sudo nano /etc/systemd/system/kestrel-aspnetcore.service

[Unit]
Description=Example .NET Web API App running on Ubuntu

[Service]
WorkingDirectory=/home/cehui0303/wwwroot/webgis  //这个地方必须填写应用程序路径，否则wwwroot下的静态资源路径可能不对，例如
ExecStart=/usr/bin/dotnet /var/www/helloapp/helloapp.dll
Restart=always
# Restart service after 10 seconds if the dotnet service crashes:
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=dotnet-example
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false

[Install]
WantedBy=multi-user.target

