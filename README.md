# 1 简介
通过添加自定义头部和自定义内容实现了两套主题：CSS渐变和自定义背景。
## 1.1 使用环境
OpenList v4.1.1
## 1.2 食用方法
进入OpenList管理后台-->设置-->全局-->将代码填入自定义头部和自定义内容-->保存
# 2 CSS渐变主题
- 将网站字体修改为`lxgwwenkai-regular`
- 修改主列表、说明栏等背景为透明玻璃风格
- 修改背景为CSS渐变
- 去除原有底部字体，引入一言API提供一句话服务

<img width="4579" height="1329" alt="image" src="https://github.com/user-attachments/assets/e38969c0-adf7-4d20-a4b7-1900da5151c7" />

## 2.1 自定义头部代码
```html
<script src="https://polyfill.alicdn.com/v3/polyfill.min.js?features=String.prototype.replaceAll"></script>
<link rel="stylesheet" href="https://npm.elemecdn.com/lxgw-wenkai-webfont@1.1.0/lxgwwenkai-regular.css" />
<style>
/* 去除通知栏 右上角 X */
 .notify-render .hope-close-button {
    display: none;
}

/*主列表白天模式透明*/
 .obj-box.hope-stack.hope-c-dhzjXW.hope-c-PJLV.hope-c-PJLV-igScBhH-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
/*主列表夜间模式透明*/
 .obj-box.hope-stack.hope-c-dhzjXW.hope-c-PJLV.hope-c-PJLV-iigjoxS-css {
    background-color:rgb(0 0 0 / 50%) !important;
}
/*readme白天模式透明*/
 .hope-c-PJLV.hope-c-PJLV-ikSuVsl-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
/*readme夜间模式透明*/
 .hope-c-PJLV.hope-c-PJLV-iiuDLME-css {
    background-color:rgb(0 0 0 / 50%) !important;
}
/*顶部右上角切换按钮透明*/
 .hope-ui-light .hope-c-ivMHWx-hZistB-cv.hope-icon-button {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-ivMHWx-hZistB-cv.hope-icon-button {
    background-color:rgb(0 0 0 / 50%) !important;
}
/*右下角侧边栏按钮透明 第一个是白天 第二个是夜间*/
 .hope-ui-light .hope-c-PJLV-ijgzmFG-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-PJLV-ijgzmFG-css {
    background-color:rgb(0 0 0 / 50%) !important;
}
/*白天模式代码块透明*/
 .hope-ui-light pre {
    background-color: rgba(255, 255, 255, 0.1)!important;
}
/*夜间模式代码块透明*/
 .hope-ui-dark pre {
    background-color: rgba(255, 255, 255, 0)!important;
}
/*左侧侧边栏目录*/
/*白天模式*/
 .hope-ui-light .hope-c-PJLV-ieGWMbI-css {
    background: rgba(255, 255, 255, 0.5) !important;
}
/*夜间模式*/
 .hope-ui-dark .hope-c-PJLV-ieGWMbI-css {
    background-color:rgb(0 0 0 / 50%) !important;
}
/* 返回顶部 */
 .hope-c-PJLV-ihVEsOa-css {
    background: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-PJLV-ihVEsOa-css {
    background-color:rgb(0 0 0 / 50%) !important;
}

/* --- MODIFIED --- 导航条完全透明 --- */
.hope-c-PJLV-ikaMhsQ-css, 
.hope-c-PJLV-icWrYmg-css,
.hope-ui-light .hope-c-PJLV-idaeksS-css,
.hope-ui-dark .hope-c-PJLV-idaeksS-css {
    background: transparent !important;
}


/* --- 修复代码开始 --- */

/* 1. 将整个应用容器设置为 Flexbox 布局 */
.App {
    display: flex;
    flex-direction: column; /* 设置主轴为垂直方向 */
    min-height: 100vh;     /* 确保应用容器至少占满整个屏幕的高度 */
}

/* 2. 让主内容区域自动伸展，填满所有可用空间 */
/* 这样当内容不足时，就会把下方的 .dibu "推" 到屏幕底部 */
.obj-box {
    flex-grow: 1;
}

/* 3. 移除 .dibu 的 fixed 定位，让它回归正常的文档流 */
.dibu {
    text-align: center;      /* 文本居中 */
    padding-bottom: 20px;    /* 底部留出 20px 间距，看起来更美观 */
    line-height: 20px;
    font-size: 9pt;
    font-weight: bold;
}

/* --- 修复代码结束 --- */

.table {
    margin: auto;
}
/*去掉底部*/
.footer {
    display: none !important;
}
/*全局字体*/
*{font-family:LXGW WenKai}
*{font-weight:bold}
body {font-family: LXGW WenKai;}
 /*渐变背景CSS*/
  #canvas-basic {
    position: fixed;
    display: block;
    width: 100%;
    height: 100%;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -999;
  }
</style>
```
## 2.2 自定义内容代码
```html
<div id="customize" style="display: none;">
    <div class="dibu">
        <span style="font-weight: bold;" id="hitokoto">
            <a href="#" id="hitokoto_text">
                "147258369."
            </a>
        </span>
        <p style="font-size: 8pt;">
            <small>
                —— Tom2077
            </small>
        </p>
    </div>
    <script src="https://v1.hitokoto.cn/?encode=js&select=%23hitokoto" defer></script>
</div>

<canvas id="canvas-basic"></canvas>
<script src="https://npm.elemecdn.com/granim@2.0.0/dist/granim.min.js"></script>
<script>
var granimInstance = new Granim({
    element: '#canvas-basic',
    direction: 'left-right',
    isPausedWhenNotInView: true,
    states : {
        "default-state": {
            gradients: [
                ['#9890e3', '#b1f4cf'],
                ['#a18cd1', '#fbc2eb'],
                ['#fff1eb', '#ace0f9'],
                ['#d4fc79', '#96e6a1'],
                ['#a1c4fd', '#c2e9fb'],
                ['#a8edea', '#fed6e3'],
                ['#a1c4fd', '#c2e9fb'],
                ['#fff1eb', '#ace0f9']
            ]
        }
    }
});
</script>

<script>
    let interval = setInterval(() => {
        if (document.querySelector(".obj-box")) {
            // 将自定义内容插入到主内容框之后
            document.querySelector(".obj-box").after(document.querySelector("#customize"));
            document.querySelector("#customize").style.display = "";
            clearInterval(interval);
        }
    }, 200);
</script>
```
# 3 自定义背景主题
- 将网站字体修改为`lxgwwenkai-regular`
- 修改导航栏、主列表、说明栏等背景为透明玻璃风格
- 修改背景为自定义图片（演示为原神茜特菈莉）
- 去除原有底部字体，引入一言API提供一句话服务

<img width="4561" height="1336" alt="image" src="https://github.com/user-attachments/assets/944b8430-ebea-498b-9c3a-466ead4939e9" />

>记得将白天背景图和夜间背景图中`background-image: url("https://www.example.com") !important;`的`https://www.example.com`换成自己喜欢的背景

## 3.1 自定义头部代码
```html
<script src="https://polyfill.alicdn.com/v3/polyfill.min.js?features=String.prototype.replaceAll"></script>

<link rel="stylesheet" href="https://npm.elemecdn.com/lxgw-wenkai-webfont@1.1.0/lxgwwenkai-regular.css" />


<style>

/* --- 粘性页脚修复代码 开始 --- */

/* 1. 将 body 设置为 flex 容器，并确保其最小高度为100%视窗高度 */
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

/* 2. 让你自定义的页脚容器自动撑开剩余空间 */
#customize {
    margin-top: auto;
}

/* --- 粘性页脚修复代码 结束 --- */

/* 去除通知栏 右上角 X */
 .notify-render .hope-close-button {
    display: none;
}

/*白天背景图*/
.hope-ui-light {
    position: relative; 
    overflow: auto; /* 从 hidden 修改为 auto */
}

.hope-ui-light::before {
    content: ''; 
    background-image: url("https://www.example.com") !important;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    filter: blur(0px); 
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1; 
    transform: scale(1.05); 
}

/*夜间背景图*/
.hope-ui-dark {
    position: relative;
    overflow: auto;
}

.hope-ui-dark::before {
    content: '';
    background-image: url("https://www.example.com") !important;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    filter: blur(0px);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    transform: scale(1.05);
}


/*主列表白天模式透明*/
 .obj-box.hope-stack.hope-c-dhzjXW.hope-c-PJLV.hope-c-PJLV-igScBhH-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
/*主列表夜间模式透明*/
 .obj-box.hope-stack.hope-c-dhzjXW.hope-c-PJLV.hope-c-PJLV-iigjoxS-css {
    background-color:rgb(0 0 0 / 50%) !important;
}
/*readme白天模式透明*/
 .hope-c-PJLV.hope-c-PJLV-ikSuVsl-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
/*readme夜间模式透明*/
 .hope-c-PJLV.hope-c-PJLV-iiuDLME-css {
    background-color:rgb(0 0 0 / 50%) !important;
}

/*顶部右上角切换按钮透明*/
 .hope-ui-light .hope-c-ivMHWx-hZistB-cv.hope-icon-button {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-ivMHWx-hZistB-cv.hope-icon-button {
    background-color:rgb(0 0 0 / 50%) !important;
}

/*右下角侧边栏按钮透明 第一个是白天 第二个是夜间*/
 .hope-ui-light .hope-c-PJLV-ijgzmFG-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-PJLV-ijgzmFG-css {
    background-color:rgb(0 0 0 / 50%) !important;
}

/*白天模式代码块透明*/
 .hope-ui-light pre {
    background-color: rgba(255, 255, 255, 0.1)!important;
}
/*夜间模式代码块透明*/
 .hope-ui-dark pre {
    background-color: rgba(255, 255, 255, 0)!important;
}

/*左侧侧边栏目录*/
/*白天模式*/
 .hope-ui-light .hope-c-PJLV-ieGWMbI-css {
    background: rgba(255, 255, 255, 0.5) !important;
}
/*夜间模式*/
 .hope-ui-dark .hope-c-PJLV-ieGWMbI-css {
    background-color:rgb(0 0 0 / 50%) !important;
}

/* 返回顶部 */
 .hope-c-PJLV-ihVEsOa-css {
    background: rgba(255, 255, 255, 0.5) !important;
}
.hope-ui-dark .hope-c-PJLV-ihVEsOa-css {
    background-color:rgb(0 0 0 / 50%) !important;
}

/*正常情况未使用吸附功能*/
/*顶部*/
 .hope-c-PJLV-ikaMhsQ-css {
    background: rgba(255, 255, 255, 0) !important;
}
/*导航条*/ 
/*白天模式*/
 .hope-ui-light .hope-c-PJLV-idaeksS-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
    border-radius: var(--hope-radii-xl) !important;
}
/*夜间模式*/
 .hope-ui-dark .hope-c-PJLV-idaeksS-css {
    background-color:rgb(0 0 0 / 50%) !important;
    border-radius: var(--hope-radii-xl) !important;
}
/* 吸附到页面顶部 */
/*顶部*/
 .hope-c-PJLV-icWrYmg-css {
    background: rgba(255, 255, 255, 0) !important;
}
/*导航条*/
 .hope-c-PJLV-icKsjdm-css::after {
    background: rgba(255, 255, 255, 0) !important;
}
/*白天模式*/
 .hope-ui-light .hope-c-PJLV-icKsjdm-css {
    background-color: rgba(255, 255, 255, 0.5) !important;
    border-radius: var(--hope-radii-xl) !important;
}
/*夜间模式*/
 .hope-ui-dark .hope-c-PJLV-icKsjdm-css {
    background-color:rgb(0 0 0 / 50%) !important;
    border-radius: var(--hope-radii-xl) !important;
}

/*仅吸附导航栏*/
/*导航条*/
 .hope-c-PJLV-ifdXShc-css::after {
    background: rgba(241, 10, 10, 0) !important;
}
/*白天模式*/
 .hope-ui-light .hope-c-hrsMRY {
    /* 将透明度从 0 修改为 0.5 */
    background-color: rgba(255, 255, 255, 0.5) !important;
    border-radius: var(--hope-radii-xl) !important;
}
/*夜间模式*/
 .hope-ui-dark .hope-c-hrsMRY {
    /* 将完全透明修改为半透明黑色 */
    background-color: rgb(0 0 0 / 50%) !important;
    border-radius: var(--hope-radii-xl) !important;
}


/* --- THIS IS THE MODIFIED PART --- */
/*底部CSS*/
.dibu {
    position: relative; /* 将 "fixed" 修改为 "relative" */
    /* bottom: 0; -- 删除或者注释掉这一行 */
    z-index: 10;
    transition: all 0.2s ease-in-out;
    margin-top: 0.5rem; /* 增加一个上边距，和主内容区隔开 */
}
/*dibu白天模式透明*/
 .hope-ui-light .dibu {
    background-color: rgba(255, 255, 255, 0.5) !important;
    /* 修改这一行，实现上圆下直的效果 */
    border-radius: var(--hope-radii-xl) var(--hope-radii-xl) 0 0 !important;
    padding: 10px;
}
/*dibu夜间模式透明*/
 .hope-ui-dark .dibu {
    background-color:rgb(0 0 0 / 50%) !important;
    /* 修改这一行，实现上圆下直的效果 */
    border-radius: var(--hope-radii-xl) var(--hope-radii-xl) 0 0 !important;
    padding: 10px;
}

/*去掉底部*/
.footer {
    display: none !important;
}

/*全局字体*/
*{font-family:LXGW WenKai}
*{font-weight:bold}
body {font-family: LXGW WenKai;}

 /*渐变背景CSS*/
  /* #canvas-basic {
    position: fixed;
    display: block;
    width: 100%;
    height: 100%;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -999;
  } */
</style>
```
## 3.2 自定义内容代码
```html
<div id="customize" style="display: none; visibility: hidden;"> <center class="dibu">
        <div style=" line-height: 20px;font-size: 9pt;font-weight: bold;">
            <span>
                <span style="font-weight: bold;" id="hitokoto">
                    <a href="#" id="hitokoto_text">
                        "Loading..."
                    </a>
                </span>
            </span>
            <p style="margin-left: 10rem;font-size: 8pt;">
                <small>
                    —— Tom2077
                </small>
            </p>
        </div>
    </center>

    <script src="https://v1.hitokoto.cn/?encode=js&select=%23hitokoto" defer></script>
</div>

<script>
    const customContent = document.querySelector("#customize");
    const footer = customContent.querySelector(".dibu");

    // This function aligns the footer to the main content box
    function alignFooter() {
        const objBox = document.querySelector(".obj-box");
        if (objBox && footer) {
            const rect = objBox.getBoundingClientRect();
            footer.style.width = rect.width + 'px';
            footer.style.left = rect.left + 'px';
            customContent.style.visibility = "visible"; // Make it visible after positioning
        }
    }

    // Run alignment logic when the page is ready
    let interval = setInterval(() => {
        if (document.querySelector(".obj-box")) {
            document.body.appendChild(customContent);
            customContent.style.display = "";
            alignFooter();
            clearInterval(interval);
        }
    }, 200);

    // Re-align the footer whenever the window is resized
    window.addEventListener('resize', alignFooter);

</script>
```
