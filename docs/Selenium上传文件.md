## Selenium自动化测试（八）之上传文件
### 第一种：直接使用`send_keys`
**注意：只针对input表单上传文件才可以使用**
```python
# 定位到input表单上传文件的元素
ele = driver.find_element_by_id("upload")
# 使用send_keys上传文件
ele.send_keys("D:\title.png")
```

### 第二种：使用`pyautogui`
有些时候上传文件使用的并不是input表单，此时就没有办法使用第一种方式进行上传了，那么我们就可以使用`pyautogui`进行模拟鼠标操作来上传文件。
#### 1）安装`pyautogui`模块
```bash
pip install pyautogui
```
#### 2）导入`pyautogui`模块
```python
import pyautogui
```
#### 3）使用`pyautogui`模拟鼠标点击
**注意：建议最大化浏览器进行坐标定位`driver.maximize_window()`**

**坐标定位可以借助于截图工具**
```python
# 通过坐标定位到上传文件按钮
pyautogui.moveTo(39, 156)
# 点击按钮，弹出资源文件弹框
pyautogui.click()
# 设置强制等待，等待弹出框弹出（不设置的话会出现输入上传的文件名混乱）
time.sleep(3)
# 通过write输入要上传的文件名
pyautogui.write(r'D:\title.png', interval=0.2)
# 点击回车进行上传
pyautogui.press('enter', presses=2)
```