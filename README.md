# Day3
写了一道力扣
今天写了一道回型矩阵，想起来大一上就写过，当时让我印象最深，也是最打击我的一道题，让我想了3个小时最后还是报错。今天有幸再次碰到。
自己的方法有问题，最后还是请教了gpt大神
https://leetcode.cn/problems/spiral-matrix-ii/
答案核心
vector<vector<int>> matrix(n,vector<int>(n,0));

int num;每次增加的数
int top = 0, bottom = n - 1, left = 0, right = n - 1;每次换方向
while(top<=bottom&&left<=right)
{
for(int i=left;i<=right;i++){
matrix[top][i]=num;
num++
}
top++;变到下一行
for(int i=top;i<=bottom;i++){
matrix[i][right]=num;
num++
}
right--;右边缩小一列
if(top<=bottom){     //gpt说需要判断，我吧这句话和下面一样的这句话删了照样可以通过 速度还快了很多。
for(int i=right;i>=left;i--){
matrix[bottom][i]=num;
num++
}
bottom++;往上升一行
}
if(left<=right){
for(int i=bottom;i>=bottom;i++){
matrix[i][left]=num;
num++
}
bottom++;往上升一行
}
}

