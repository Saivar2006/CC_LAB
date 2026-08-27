# Ex.No: 02-Virtual-Machine-C-Compiler

# Virtual Machine – C Compiler

## AIM

Install a C compiler in the virtual machine created using a virtual box and execute Simple Programs.

## ALGORITHM

1. Install the VMware player and host the Virtual Machine (CorePlus).
2. Open VMware Workstation and power on the virtual machine.
3. After the guest operating system loads, open the terminal.
4. Install the compiler and required libraries using `tce-load -wi compiletc`.
5. Open the terminal editor using the procedure in the manual.
6. Type the C program and save it with a `.c` extension.
7. Exit the editor using CTRL+Q.
8. Compile the program using `cc filename.c`.
9. Execute the program using `./a.out`.
10. Enter the requested input and verify the output.

## PROGRAM / CODE

```text
#include <stdio.h>

int main()
{
    int year;

    printf("Enter year: ");
    scanf("%d", &year);

    if ((year % 400 == 0) || (year % 100 != 0 && year % 4 == 0))
        printf("%d is a Leap Year\n", year);
    else
        printf("%d is not a Leap Year\n", year);

    return 0;
}
```

## SAMPLE INPUT

```text
1991
```

## SAMPLE OUTPUT

```text
Enter year: 1991
1991 is not a Leap Year
```

## RESULT

Thus the Install a C compiler in the virtual machine created using a virtual box and execute Simple Programs.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
