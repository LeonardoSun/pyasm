# pyasm
pyasm for python 3.+
build on upon Florian Boesch's pyasm project.

currently working on hello world example
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
