# jimengaiprompt

# 即梦AI绘画提示词生成网站 README

## 项目简介
即梦AI绘画提示词生成网站是一款用于生成高质量AI绘画提示词的工具。用户可以通过选择不同的参数组合，如光影与照明、镜头与构图、环境场景、艺术风格等，自动生成详细的提示词，并支持一键复制到剪贴板。该工具旨在帮助艺术家和设计师快速生成符合需求的AI绘画提示词，提高工作效率。

## 功能特点
- **丰富的参数选项**：提供多种分类模块，包括光影与照明、镜头与构图、环境场景、艺术风格、色彩与材质、艺术媒介、年代风格、情感表达和色彩方案等。
- **自定义选项**：用户可以添加自定义选项，保存到本地存储，方便下次使用。
- **一键生成提示词**：点击按钮即可生成包含所有选中参数的高级提示词。
- **一键复制**：生成的提示词可以直接复制到剪贴板，方便粘贴到其他应用中。
- **折叠式分类模块**：通过点击标题展开或收起内容，提升用户体验。

## 使用说明

### 页面结构
1. **主体描述**
   - 用户可以在输入框中自由输入主题描述，例如“戴VR眼镜的上班族”、“手握光剑的柴犬”等。

2. **分类模块**
   - 每个分类模块（如光影与照明、镜头与构图等）都包含多个复选框，用户可以选择需要的参数。
   - 模块标题为可折叠样式，点击标题可以展开或收起内容。

3. **自定义选项**
   - 每个分类模块底部提供了一个输入框和按钮，用户可以在此添加自定义选项并保存。

4. **生成提示词**
   - 点击“🚀 生成高级提示词”按钮，系统会根据用户的选择生成提示词，并显示在页面下方的输出区域。

5. **复制提示词**
   - 点击“一键复制”按钮，可以将生成的提示词复制到剪贴板。

### 示例
1. 输入主体描述：“戴VR眼镜的上班族”
2. 选择光影与照明中的“戏剧灯光”，镜头与构图中的“电影镜头”，环境场景中的“未来都市”等。
3. 点击“🚀 生成高级提示词”按钮，生成的提示词可能如下：
   ```
   戴VR眼镜的上班族, 戏剧灯光, 电影镜头, 未来都市, 8K超高清画质
   ```

## 技术实现
- **HTML/CSS/JavaScript**：前端页面使用HTML5、CSS3和JavaScript编写，确保兼容性和响应式设计。
- **本地存储**：使用浏览器的`localStorage`保存用户的自定义选项，避免刷新页面后数据丢失。
- **事件处理**：通过JavaScript监听用户交互事件，如点击、输入等，动态更新页面内容。

## 开发者指南
- **文件结构**
  - `index.html`：主页面文件，包含HTML结构和部分样式。
  - `style.css`：外部样式表文件，包含页面的样式定义。
  - `script.js`：外部脚本文件，包含页面的交互逻辑。

- **代码示例**
  - **折叠功能**：
    ```javascript
    function toggleCollapse(element) {
        const content = element.nextElementSibling;
        if (content.style.display === 'block') {
            content.style.display = 'none';
        } else {
            content.style.display = 'block';
        }
    }
    ```

  - **生成提示词**：
    ```javascript
    function generateSmartPrompt() {
        const mainSubject = document.getElementById('mainSubject').value;
        const selectedParams = [];
        document.querySelectorAll('input[type="checkbox"]:checked').forEach(checkbox => {
            selectedParams.push(checkbox.value);
        });

        const finalPrompt = `${mainSubject}, ${selectedParams.join(', ')}, 8K超高清画质`;
        document.getElementById('output').textContent = finalPrompt;
    }
    ```

  - **复制提示词**：
    ```javascript
    function copyPrompt() {
        const text = document.getElementById('output').textContent;
        navigator.clipboard.writeText(text).then(() => {
            alert('提示词已复制到剪贴板！');
        });
    }
    ```

## 常见问题

- **生成的提示词格式是什么样的？**
  - 提示词由用户输入的主体描述和选中的参数组成，以逗号分隔，并在末尾添加“8K超高清画质”。

- **是否支持移动端？**
  - 是的，页面采用响应式设计，支持各种屏幕尺寸。

## 联系方式
如果您有任何问题或建议，请联系开发者邮箱：93329385@qq.com。

---

希望这个README文件能帮助您更好地理解和使用AI提示词生成器。祝您创作愉快！
