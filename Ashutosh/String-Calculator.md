# Title: Array-JumpGame

Question link: https://leetcode.com/problems/basic-calculator-ii/

### Code:

```
class Solution {
public:
    int calculate(string s)
{
	vector<int> values;
	vector<int> prevValues;
	int index1 = 0;

	for (int i = 0; i < s.size(); i++)
	{
		if (s[i] == '*' || s[i] == '/')
		{
			int temp1 = i - 1;
			while (temp1 >= 0 && s[temp1] == ' ')
				temp1--;
			int num1;
			if(s[temp1] == '#')
			{
				s[temp1] = ' ';
				num1 = values[values.size()-1];
				values.pop_back();
			}
			else
			{
				num1 = s[temp1] - '0';
				s[temp1] = ' ';
				temp1--;
				int exp = 1;
				while (temp1 >= 0 && isdigit(s[temp1]))
				{
					num1 += ((s[temp1] - '0') * pow(10, exp));
					s[temp1] = ' ';
					temp1--;
					exp++;
				}
			}

			int temp2 = i + 1;
			while (temp2 < s.size() && s[temp2] == ' ')
				temp2++;
			int num2;
			if (s[temp2] == '#')
			{
				s[temp2] = ' ';
				num2 = values[values.size()-1];
				values.pop_back();
			}
			else
			{
				num2 = s[temp2] - '0';
				s[temp2] = ' ';
				temp2++;
				while (temp2 < s.size() && isdigit(s[temp2]))
				{
					num2 *= 10;
					num2 += (s[temp2] - '0');
					s[temp2] = ' ';
					temp2++;
				}
			}


			if (s[i] == '*')
				values.push_back(num1 * num2);
			else
				values.push_back(num1 / num2);

			s[i] = ' ';
			temp2--;
			s[temp2] = '#';
		}
	}

	for (int i = 0; i < s.size(); i++)
	{
		if (s[i] == '+' || s[i] == '-')
		{
			int temp1 = i - 1;
			int num1;
			while (temp1 >= 0 && s[temp1] == ' ')
				temp1--;
			if (s[temp1] == '#')
			{
				s[temp1] = ' ';
				num1 = values[index1];
				index1++;
			}
			else if (s[temp1] == '@')
			{
				s[temp1] = ' ';
				num1 = prevValues[prevValues.size()-1];
				prevValues.pop_back();
			}
			else
			{
				num1 = s[temp1] - '0';
				s[temp1] = ' ';
				temp1--;
				int exp = 1;
				while (temp1 >= 0 && isdigit(s[temp1]))
				{
					num1 += ((s[temp1] - '0') * pow(10, exp));
					s[temp1] = ' ';
					temp1--;
					exp++;
				}
			}

			int temp2 = i + 1;
			int num2;
			while (temp2 < s.size() && s[temp2] == ' ')
				temp2++;
			if (s[temp2] == '#')
			{
				s[temp2] = ' ';
				num2 = values[index1];
				index1++;
			}
			else if (s[temp2] == '@')
			{
				s[temp2] = ' ';
				num2 = prevValues[prevValues.size()-1];
				prevValues.pop_back();
			}
			else
			{
				num2 = s[temp2] - '0';
				s[temp2] = ' ';
				temp2++;
				while (temp2 < s.size() && isdigit(s[temp2]))
				{
					num2 *= 10;
					num2 += (s[temp2] - '0');
					s[temp2] = ' ';
					temp2++;
				}
			}

			if (s[i] == '+')
				prevValues.push_back(num1 + num2);
			else
				prevValues.push_back(num1 - num2);

			s[i] = ' ';
			temp2--;
			s[temp2] = '@';
		}
	}

	for (int i = s.size() - 1; i >= 0; i--)
	{
		if (s[i] == ' ')
			continue;
		if (s[i] == '#')
			return values[values.size() - 1];
		if (s[i] == '@')
			return prevValues[prevValues.size() - 1];
		int num = 0;
		int exp = 0;
		while (i >= 0 && isdigit(s[i]))
		{
			num += ((s[i] - '0') * pow(10, exp));
			exp++;
			i--;
		}
		return num;
	}

	return 0;
}
};
```

### Output:


### Comments:
