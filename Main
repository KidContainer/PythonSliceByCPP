#include<vector>
#include<iostream>
#include<iterator>
#include<algorithm>
using namespace std;

void print(int a) {
	cout << a << "  ";
}

class List {
private:
	vector<int> vec;
public:
	List() {
		vec = vector<int>{ 1,2,3,4,5,6,7,8,9 };
	}
	void operator () () {
		for_each(vec.begin(), vec.end(), print);
		cout << endl;
	}
	void operator()(int beg) {
		auto firstOut = vec.begin();
		if (beg < 0) {
			auto newBeg = beg + vec.size();
			firstOut = vec.begin() + newBeg;
		}
		else {
			firstOut = vec.begin()+beg;
		}
		for_each(firstOut, vec.end(), print);
		cout << endl;
	}
	void operator()(int beg, int end,int step=1) {
		vector<int>::iterator first, last;
		if (beg > 0) {
			first = vec.begin() + beg;
		}
		if (end > 0) {
			last = vec.end() - (vec.size() - end);
		}
		if (beg < 0) {
			auto newBeg = beg + vec.size();
			first = vec.begin() + newBeg;
		}
		if (end < 0) {
			auto newEnd = end + vec.size();
			last = vec.begin() + newEnd;
		}
		if (beg == 0) first = vec.begin();
		if (end == 0) last = vec.end();
		if(step==1)  for_each(first, last, print);
		if (step > 1) {
			vector<int> out;
			for (auto temp = first;; temp = temp + step) {
				out.push_back(*temp);
				if (last - temp < step) break;
			}

			for_each(out.begin(), out.end(), print);

		}
		cout << endl;
	}

};

int main() {
	List l;
	l();
	l(1);
	l(0 , 3);
	l(-1);
	l(1, -1);
	l(0, 0, 2);

	system("pause");
	return 0;
}
