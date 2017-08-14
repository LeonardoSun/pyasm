# pyasm
pyasm for python 3.+

Build on upon Florian Boesch's pyasm project.

I thought the original project could work in python 2.+ at first,
but recently when I run the code in 2.+ there are some errors either.
So this project is paused.

But I like the idea with it's coding style, may be continue in the future.


> Hello World example:
```python
    from pyasm import Program
    from pyasm.data import String
    from pyasm.macro import syscall
    from pyasm.instructions import mov, ret, push, add
    from pyasm.registers import eax, ebx, ecx, edx, ebp
    import sys

    def example():
        msg = 'Hello World!'
        prog = Program(
            mov(ebx, 1),
            mov(ecx, String(msg)),
            mov(edx, len(msg)),
            syscall('write'),
            ret(),
        )
        fun = prog.compile()
        fun()

    if __name__ == '__main__':
        example()
```
