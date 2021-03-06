# Link Server Plugin
该插件将会打开一个端口3333的反向代理服务器用于从Obsidian API中获取Wiki链接的文件信息
```
// 该插件将会返回obsidian api的筛选结果 `plugin.app.metadataCache.getFirstLinkpathDest(<string>fileLink, <string>sourcePath);`
// 通过使用 http://localhost:3333/?fileLink=<wiki原链接>&sourcePath=<md文件路径> 获取TFile类型的json数据
type TFile = {
    basename: string,
    extension: string
    name: string, 
    parent: {
        name: string,
        path: string
    },
    path: string,
    vault: {
        adapter: {
            basePath: string
        }
    },
    content: string
}
```

This plugin will open a reverse proxy server at port 3333 to get wikiLink information Obsidian API.
```
// this plugin will retrun `plugin.app.metadataCache.getFirstLinkpathDest(<string>fileLink, <string>sourcePath);` result
// by using http://localhost:3333/?fileLink=<wikiLink>&sourcePath=<mdFilePath> to get json data based on below TFile
type TFile = {
    basename: string,
    extension: string
    name: string, 
    parent: {
        name: string,
        path: string
    },
    path: string,
    vault: {
        adapter: {
            basePath: string
        }
    },
    content: string
}
```

## How to use

注意：该插件会打开一个默认端口3333的反向代理服务器，若该端口不可用，请到Link Server的设置页中修改端口

Note: This plugin will open a reverse proxy server at port 3333 by default. If the port is used, please go to the setting tab of Link Server to set another port

***

1. 安装该插件 Install the plugin
2. 在`第三方插件`中启用该插件 Enable the plugin in `Community Plugins`
3. 开始使用插件 The plugin is ready to use

## Compatibility

The required API feature is only available for Obsidian v0.12.2+.

## Installation

### From Obsidian

1. Open `Settings` > `Third-party plugin`
2. Make sure Safe mode is **off**
3. Click `Browse community plugins`
4. Search for this plugin
5. Click `Install`
6. Once installed, enable this plugin and close the community plugins window and the plugin is ready to use.

***

1. 打开`设置`>`第三方插件`
2. 确保安全模式为`关闭`
3. 点击`浏览社区插件`
4. 搜索此插件
5. 点击`安装`
6. 安装完成后，启用该插件并关闭安装窗口，插件即可使用

### From GitHub

1. Download the Latest Release from the Releases section of the GitHub Repository
2. Put files to your vault's plugins folder: `<vault>/.obsidian/plugins/link-info-server`  
3. Reload Obsidian
4. If prompted about Safe Mode, you can disable safe mode and enable the plugin.
Otherwise, head to Settings, third-party plugins, make sure safe mode is off and
enable the plugin from there.

> Note: The `.obsidian` folder may be hidden. On macOS, you should be able to press `Command+Shift+Dot` to show the folder in Finder.

***

1. 从GitHub仓库的Releases下载最新版本
2. 把文件放在对应Vault的插件文件夹下：`<vault>/.obsidian/plugins/link-info-server`
3. 重新加载Obsidian
4. 如果出现有关安全模式的提示，则可以禁用安全模式并启用插件。否则，请转到`设置`→`第三方插件`，确保关闭安全模式，然后从`第三方插件`启用插件

> 注意，`.obsidian`文件夹为隐藏文件夹，在macOS的Finder下可以按`Command+Shift+.`以显示隐藏文件夹
