# cUnit.
Just another simple header unit testing framework for C language.

# Supported platforms.

Current version supports Linux/POSIX OS and gcc compiler only.

# Usage.
Just `#include "cunit.h"` header in your code.

## Main routine
There are defined two special macros: `CUNIT_MAIN` and `CUNIT_GLOBALS`. First one declares a main function with cunit main routine execution and the second one declares a global context variable.

## Example.
``` C
#include "cunit.h"

CUNIT_GLOBALS;

CUNIT_MAIN();
```

If you need to execute some extra code in the main routine, the following code might be used:
``` C
#include "cunit.h"

CUNIT_GLOBALS;

int main(int argc, char *argv[]) {
    return cunit_main(argc, argv[]);
}
```

## Testing macros.

There two groups of macros `CUNIT_EXPECT_*` and `CUNIT_ASSERT_*`. Expect macros does not interrupt current test case in case of failure, just notify about the issue and continue. Assert macros interrupts current test case in case of failure.

The following macros are already implemented:
``` C
CUNIT_ASSERT_TRUE(__cond);
CUNIT_ASSERT_FALSE(__cond);

CUNIT_EXPECT_TRUE(__cond);
CUNIT_EXPECT_FALSE(__cond);

CUNIT_ASSERT_EQ(__val1, __val2)
CUNIT_ASSERT_NE(__val1, __val2)
CUNIT_ASSERT_LT(__val1, __val2)
CUNIT_ASSERT_LE(__val1, __val2)
CUNIT_ASSERT_GT(__val1, __val2)
CUNIT_ASSERT_GE(__val1, __val2)

CUNIT_EXPECT_EQ(__val1, __val2)
CUNIT_EXPECT_NE(__val1, __val2)
CUNIT_EXPECT_LT(__val1, __val2)
CUNIT_EXPECT_LE(__val1, __val2)
CUNIT_EXPECT_GT(__val1, __val2)
CUNIT_EXPECT_GE(__val1, __val2)
```
