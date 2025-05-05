This repository provides an implementation of the Happy Number Algorithm in both C and RISC-V Assembly. A Happy Number is defined based on a simple iterative process: starting with any positive integer, replace the number with the sum of the squares of its digits. Repeat the process until the number equals 1 (happy), or loops endlessly without reaching 1 (unhappy).

📚 Algorithm Description
Happy Number Theorem:

Starting with n, replace it with the sum of the squares of its digits. Repeat the process until n == 1 (then it’s a happy number), or you enter a cycle that does not include 1 (then it’s not a happy number).

🔁 Example
Input: n = 19
1² + 9² = 82 → 8² + 2² = 68 → 6² + 8² = 100 → 1² + 0² + 0² = 1
✅ Output: true

Input: n = 2
This process loops without reaching 1.
❌ Output: false

💻 C Implementation
📄 File: happy_number.c

#include<stdio.h>

int main() {
    int n = 2, sum = 0, rem;

    while(n > 0) {
        rem = n % 10;
        sum += rem * rem;
        n = n / 10;

        if(n == 0 && sum >= 10) {
            n = sum;
            sum = 0;
        }
    }

    if(sum == 1) {
        printf("true");
    } else {
        printf("false");
    }
}
✅ Compile and Run

gcc happy_number.c -o happy_number
./happy_number
🧾 RISC-V Assembly Implementation
📄 File: happy_number.s
Written in standard RISC-V Assembly

Uses system calls (ecall) for console output

Handles sum of digit squares and loop detection

🔧 Required Tools
RARS or SPIKE or QEMU

RISC-V GCC toolchain (for command-line compilation)

▶️ Run in RARS
Open happy_number.s in RARS

Assemble and Run

Output will be either true or false printed to the console

🧠 Binary & Disassembly
This repo also includes:

✅ Hex and Binary Opcodes

✅ Disassembled Instructions
Useful for debugging, microarchitecture implementation, or simulator design.

📁 Directory Structure

Edit
├── happy_number.c         # C implementation
├── happy_number.s         # RISC-V Assembly implementation
├── opcodes_hex.txt        # Instruction opcodes in hexadecimal
├── opcodes_binary.txt     # Instruction opcodes in binary
├── README.md              # Project README

🙋‍♂️ Author
Prince Raj
GitHub: @RajjjPrince



