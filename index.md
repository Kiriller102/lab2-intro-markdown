# H1 example
## H2 example
##### H5 example

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)
```cpp

#include <iostream>
#include <vector>

using namespace std;

void fill(vector<vector<int>> &image,
          int sr,
          int sc,
          int color,
          int &ans) {
  image[sr][sc] = 0;
  ans++;
  if (sr - 1 >= 0 && image[sr - 1][sc] == 1) {
    fill(image, sr - 1, sc, color, ans);
  }
  if (sc - 1 >= 0 && image[sr][sc - 1] == 1) {
    fill(image, sr, sc - 1, color, ans);
  }
  if (sr + 1 < image.size() && image[sr + 1][sc] == 1) {
    fill(image, sr + 1, sc, color, ans);
  }
  if (sc + 1 < image[0].size() && image[sr][sc + 1] == 1) {
    fill(image, sr, sc + 1, color, ans);
  }
}

int main() {
  vector<vector<int>> image{{0, 0, 0}, {0, 0, 0}};
  int sr = 1;
  int sc = 1;
  int color = 2;
  fill(image, sr, sc, color, image[sr][sc]);
  for(int i = 0; i < image.size(); i++) {
    for(int j= 0 ; j < image[0].size(); j++) {
      cout << image[i][j] << ' ';
    }
    cout << '\n';
  }
}

```
