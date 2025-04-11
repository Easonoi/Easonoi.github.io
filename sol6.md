

### ✅ 解题思路

每个立方体通过输入的两个对角点（分别给出 \( (x_1, y_1, z_1) \) 和 \( (x_2, y_2, z_2) \)）确定。我们可以先对每个坐标轴分别取较小值和较大值来确定每个立方体在每个轴上的范围。

设：

- A 的范围是：`[Ax1, Ax2]`, `[Ay1, Ay2]`, `[Az1, Az2]`
- B 的范围是：`[Bx1, Bx2]`, `[By1, By2]`, `[Bz1, Bz2]`

两个立方体在三维空间中相交 **等价于**：

```
min(Ax2, Bx2) > max(Ax1, Bx1)
&& min(Ay2, By2) > max(Ay1, By1)
&& min(Az2, Bz2) > max(Az1, Bz1)
```

#### **Proof**
必要性：在 x、y、z 三个轴上都存在交集，它们的体积才可能不为 0。

充分性：假设存在两个立方体满足条件，但无交
显然存在一个平面平行于某坐标轴，使得两个立方体分居其两侧
所以在该方向上，不满足条件，与假设矛盾

---

### ✅ C++ 示例代码

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    long long x1, y1, z1, x2, y2, z2;
    long long x3, y3, z3, x4, y4, z4;

    // 输入两个立方体的对角顶点
    cin >> x1 >> y1 >> z1 >> x2 >> y2 >> z2;
    cin >> x3 >> y3 >> z3 >> x4 >> y4 >> z4;

    // 保证每个立方体的坐标范围是从小到大
    if (x1 > x2) swap(x1, x2);
    if (y1 > y2) swap(y1, y2);
    if (z1 > z2) swap(z1, z2);
    if (x3 > x4) swap(x3, x4);
    if (y3 > y4) swap(y3, y4);
    if (z3 > z4) swap(z3, z4);

    // 判断是否存在交集
    if (min(x2, x4) > max(x1, x3) &&
        min(y2, y4) > max(y1, y3) &&
        min(z2, z4) > max(z1, z3)) {
        cout << "YES\n";
    } else {
        cout << "NO\n";
    }

    return 0;
}
```

---

这个代码中用了提示中的 `swap` 函数来整理输入坐标范围，使得判断更简洁。如果你用的是 Python 或其他语言，也可以给你相应的版本～需要吗？