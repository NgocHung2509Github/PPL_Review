Ví dụ:
- Cho array: a\[1..3, 2..6, 7..15\]. Tính address của a\[2, 5, 8\]. Cho địa chỉ của element đầu tiên là 1000, size của integer là 2.
- Size của từng dimension lần lượt là s1, s2, s3: 
	- s1 = 3 
	- s2 = 5 
	- s3 = 9.
- Tính hiệu của index và lower bound a1, a2, a3: 
	- a1 = 2-1 = 1
	- a2 = 5-2 = 3
	- a3 = 8-7 = 1

### Row major
___
1. Tính theo thứ tự từ bên trái sang: $a1 * s2 * s3 + a2 * s3 + a3$ (lấy a nhân cho những s lớn hơn a). Lấy kết quá nhân với size của element, ở đây là integer nên nhân 2.
	- (1\*5\*9 + 3\*9 + 1)\*2 = 146
2. Cộng với địa chỉ của phần tử đầu tiên (ở đây là 1000):
	- 1000 + 146 = 1146

### Column major
___
1. Tính ngược lại từ phải sang: $a3*s2*s1+a2*s1+a1$ (lấy a từ lớn đến bé nhân cho những s nhỏ hơn a đó)
	- (1\*5\*3 + 3\*3 + 1)\*2 = 50
2. Cộng với địa chỉ của phần tử đầu
	- 1000 + 50 = 1050