```c
pos_group = VGroup(*pos_labels).arrange(DOWN, aligned_edge=LEFT).next_to(a_group, DOWN * 2)
`arrange(DOWN)`：垂直排列
.shift(DOWN * 0.2)
```
arrage中DOWN和RIGHT不同
```c
pos_group.submobjects[ai - 1] = new_pos
``` 
修改原object而不发生重叠

```c
self.play(
   nxt_labels[i - 1].animate.shift(HISTORY_SHIFT).set_opacity(OLD_LABEL_OPACITY)
                )
```
shift()的移动使用 HISTORY_SHIFT = LEFT * 2 左移

```c
a_text = [Text(f"a[{i}]={a[i]}").scale(0.6) for i in range(1, n + 1)]
a_group = VGroup(*a_text).arrange(RIGHT, buff=0.5)

# pos 横排
pos_labels = [Text(f"pos[{i}] = 0").scale(0.5) for i in range(1, 4)]
pos_group = VGroup(*pos_labels).arrange(RIGHT, buff=0.5)

# nxt 横排
nxt_labels = [Text(f"nxt[{i}][0] = 0").scale(0.5) for i in range(1, n + 1)]
nxt_group = VGroup(*nxt_labels).arrange(RIGHT, buff=0.5)

# 将三组垂直堆叠，从上到下显示
layout = VGroup(a_group, pos_group, nxt_group).arrange(DOWN, buff=0.8).to_edge(UP)
```
打包从上到下

```c
def show_subtitle(self, text, duration=2):
    subtitle = Text(text, font_size=24).to_edge(DOWN)
    self.play(FadeIn(subtitle))
    self.wait(duration)
    self.play(FadeOut(subtitle))
    使用
 self.show_subtitle("第二句", duration=3)
```
字幕函数

```c
   self.remove(decimal_text, decimal)
```
删除字幕

```c
step_objects = []
  self.play(
        *[FadeOut(obj) for obj in results],  # 淡出所有结果文本
        *[FadeOut(obj) for obj in step_objects],  # 淡出所有步骤文本
        run_time=1

        )
```
打包淡出

```c
 results = []

        positions = [UP * 1, DOWN * 0.5, DOWN * 2, DOWN * 3.5]
        # 计算余数的对齐位置（假设在右侧）
        align_point = positions[0] + RIGHT * 3  # 与余数文本对齐的位置
        tt.next_to(align_point, UP, buff=0.5)  # 放在第一个余数上方
        self.add(tt)
        
        result_text = Text(result, color=GREEN).move_to(positions[i] + RIGHT * 3)
```
对齐

而`shift()`方法需要的是一个**向量**（表示移动的方向和距离）

for循环排列不能直接move to（origin），会挤在一起

```c
self.show_subtitle(f"比较数字: {numbers1[compare_index]} 和 {numbers2[compare_index]}")
```
变量放{}内

```c
code_bg = SurroundingRectangle(

            code_obj,

            color=GRAY,

            fill_color=BLACK,

            fill_opacity=0.8,

            buff=0.5  # 文本与边框的间距

        )
```
编程边框加入group中