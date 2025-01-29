---
title: "Rubbish"
date: 1.29
tags: ["rubbish"]
showComments : false
draft: true
---
<!-- | add         | 功能                                                         |
| ----------- | ------------------------------------------------------------ |
| image       | **必填** 用于匹配图像名称的正则表达式或 URL。                |
| aspectRatio | **可选** 画廊的纵横比。`16-9` 、`21-9` 或`32-9` 。默认设置为`16-9` 。 |
| interval    | **可选** 自动滚动的时间间隔，以毫秒为单位指定。默认为`2000`（2 秒）。 |

| Parameter   | Description                        |
| ----------- | ---------------------------------- |
| `url`       | **必需的** 外部托管代码文件的 URL. |
| `type`      | 用于语法突出显示的代码类型.        |
| `startLine` | **可选** 从代码文件中导入的起始行. |
| `endLine`   | **可选** 从代码文件中导入的结束行. |

| 参数      | 功能                                                         |
| --------- | ------------------------------------------------------------ |
| `src`     | **必填** 图像的本地路径/文件名或 URL。当提供路径和文件名时，主题将尝试使用以下查找顺序来查找图像：首先，作为与页面绑定的[页面资源](https://gohugo.io/content-management/page-resources/)；然后是 `assets/` 目录中的文件；最后是，`static/`目录中的文件。 |
| `alt`     | 图像的[替代文本描述](https://moz.com/learn/seo/alt-text)。   |
| `caption` | Markdown 格式的图像标题，将显示在图像下方。                  |
| `class`   | 应用于图像的其他 CSS 类。                                    |
| `href`    | 图像应链接到的 URL。                                         |
| `target`  | `href` URL 的目标属性。                                      |
| `nozoom`  | `nozoom=true` 会禁用图像`缩放`功能。与 `href` 结合使用十分有用。 |
| `default` | 用于恢复默认 Hugo `figure` 行为的特殊参数。只需提供`default=true`，然后使用正常的 [Hugo 简码语法](https://gohugo.io/content-management/shortcodes/#figure)。 | -->
第一行1346第二行2345第三行123456第四行123456第五行2345第六行1346


```







输入

输出



| a    | b    | c    | d    | e    | f    | g    | h    | i    | j    | k    | l    | m    | n    | o    | p    | q    | r    | s    | t    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| h    | r    | g    | k    | y    | t    | i    | q    | l    | s    | d    | j    | n    | a    | p    | m    | b    | v    | o    | f    |
| u    | v    | w    | x    | y    | z    |      |      |      |      |      |      |      |      |      |      |      |      |      |      |
| z    | c    | x    | e    | u    | w    |      |      |      |      |      |      |      |      |      |      |      |      |      |      |

i want to drink

l xhaf fp kvlad

```
# 初始化捕虫网的起始位置
net_position = [0.0, 0.0, 0.0]  # 捕虫网初始位置
net_speed_ratio = 2  # 捕虫网与萤火虫的速度比 2:1
catch_distance = 0.1  # 捕虫网抓住萤火虫的标准距离


# 计算两个点之间的欧几里得距离
def calculate_distance(pos1, pos2):
    return math.sqrt((pos1[0] - pos2[0]) ** 2 + (pos1[1] - pos2[1]) ** 2 + (pos1[2] - pos2[2]) ** 2)


# 根据当前捕虫网与萤火虫之间的距离和位置，计算萤火虫的下一步位置
def calculate_firefly_position(net_position, distance):
    # 假设萤火虫和捕虫网的相对位置是一条直线，我们可以通过距离来估算
    # 为了简化模型，假设萤火虫沿着与捕虫网的连线方向移动
    direction = [net_position[0] + distance, net_position[1], net_position[2]]
    return direction


# 计算捕虫网的下一步目标位置
def next_net_position(firefly_position, net_position, net_speed_ratio):
    # 计算萤火虫和捕虫网的当前距离
    distance = calculate_distance(firefly_position, net_position)

    if distance <= catch_distance:
        print("捕虫网已抓住萤火虫！")
        return None

    # 捕虫网朝着萤火虫的方向移动
    direction = [firefly_position[i] - net_position[i] for i in range(3)]  # 捕虫网到萤火虫的方向向量
    magnitude = calculate_distance([0, 0, 0], direction)  # 方向向量的大小

    # 归一化方向向量
    direction = [d / magnitude for d in direction]

    # 捕虫网速度是萤火虫的两倍
    net_move = [d * net_speed_ratio for d in direction]  # 捕虫网的移动方向
    next_position = [net_position[i] + net_move[i] for i in range(3)]  # 捕虫网的下一步位置

    return next_position


# 绘制三维图形
def plot_3d(net_position, firefly_position):
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')

    # 绘制捕虫网与萤火虫的位置
    ax.scatter(net_position[0], net_position[1], net_position[2], color='blue', label='捕虫网', s=100)
    ax.scatter(firefly_position[0], firefly_position[1], firefly_position[2], color='yellow', label='萤火虫', s=100)

    # 绘制坐标轴
    ax.set_xlabel('X')
    ax.set_ylabel('Y')
    ax.set_zlabel('Z')

    # 设置图例
    ax.legend()

    # 显示图形
    plt.show()


# 模拟捕虫网每一步的移动
def run_simulation():
    global net_position
    firefly_position = [2.0, 4.0, 0.0]  # 假设萤火虫的初始位置

    while True:
        try:
            # 让用户输入当前萤火虫与捕虫网的距离
            print("请输入捕虫网与萤火虫之间的距离（大于0，退出请输入负数）：")
            distance = float(input())
            if distance < 0:
                print("退出模拟。")
                break
            if distance <= 0:
                print("距离必须大于0！")
                continue

            # 计算萤火虫的下一步位置
            firefly_position = calculate_firefly_position(net_position, distance)

            # 获取捕虫网的下一步位置
            next_position = next_net_position(firefly_position, net_position, net_speed_ratio)

            if next_position is None:
                break

            # 输出捕虫网的下一步目标位置
            print(f"捕虫网的下一步目标位置: {next_position}")

            # 更新捕虫网位置
            net_position = next_position

            # 绘制捕虫网和萤火虫的三维位置
            plot_3d(net_position, firefly_position)

        except ValueError:
            print("请输入一个有效的数字！")


# 启动模拟
run_simulation()
```

*是亮
"Pyaga dqx V tvxs iya eaqxvxb wt iya uygqka 'Fqy bzlgd rvpxa tpe sznmo pcyv fqy jhwu kpi'?"
hello
Yaffw!


tsw：fox


入 Fox pybhd mngzj tgw vylic gaxn fox rsue kgq.


出 Tpe murqk naiws fix cujlg ihea tpe vozy dib.


   The quick brown fox jumps over the lazy dog.

fax hygvd qbszm tsw lypoj srxb fax inue ksc.


Fox pybhd mngzj tgw vylic gaxn fox rsue kgq.

Uln tcvae gxsph osd bcwif sknx uln yjmq rsz.

The quick brown fox jumps over the lazy dog.
pjd efiya vktlx ctn sfuzg tbdk pjd ohqr wtm.
print
zkixp



```nzvfpm
dhe dhapdh_ohsscgh(hmapdhd_ohsscgh):
    dhapdhd_ohsscgh = ""
    epu afcu im hmapdhd_ohsscgh:
        ie afcu.iscknfc():
            dhapdhd_ohsscgh += afu((pud(afcu) - 32) % 26 + 97)
        hksh:
            dhapdhd_ohsscgh += afcu
    uhvrum dhapdhd_ohsscgh

hmapdhd_ohsscgh = "The quick brown fox jumps over the lazy dog."
dhapdhd_ohsscgh = dhapdh_ohsscgh(hmapdhd_ohsscgh)
nuimv(dhapdhd_ohsscgh)
```