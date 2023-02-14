# this

## 1.*this作为返回值，链式编程。

```c++
public:
	Person(int age) {
		this->m_age = age;
	}
	Person& add(Person &p) {
		this->m_age += p.m_age;
		return *this;
	}
public:
	int m_age;
};
int main() {
	Person p2(18);
	Person p1(18);
	p1.add(p2).add(p2).add(p2);
	cout << p1.m_age << '\n';
    system("pause");
	return 0;
}
```



```c++
public:
	Person(int age) {
		this->m_age = age;
	}
	Person add(Person &p) {
		this->m_age += p.m_age;
		return *this;
	}
public:
	int m_age;
};
int main() {
	Person p2(18);
	Person p1(18);
	p1.add(p2).add(p2).add(p2);//此时会输出36，因为这个返回值是相当于拷贝出了一个新对象。后面改变就不是p1l
	cout << p1.m_age << '\n';
    system("pause");
	return 0;
}
```

