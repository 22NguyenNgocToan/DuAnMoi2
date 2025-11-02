#include <bits/stdc++.h>
using namespace std;

string estimateComplexity(const string &code) {
    int forCount = 0;
    size_t pos = code.find("for");
    while (pos != string::npos) {
        forCount++;
        pos = code.find("for", pos + 1);
    }

    if (forCount == 0) return "O(1)";
    if (forCount == 1) return "O(n)";
    if (forCount == 2) return "O(n^2)";
    return "O(n^" + to_string(forCount) + ")";
}

int main() {
    cout << "=== AI Complexity Estimator 🔍 ===\n";
    cout << "Nhập code cần phân tích (kết thúc bằng dòng trống):\n";
    string line, input;
    while (getline(cin, line) && !line.empty()) input += line + '\n';
    cout << "\nĐộ phức tạp ước tính: " << estimateComplexity(input) << endl;
}
