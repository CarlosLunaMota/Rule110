# Rule 110
A borderless implementation of the Rule 110 cellular automaton.

**Code:**

```python
    def Rule110(universe):
        """Performs a single iteration of the Rule 110 in a borderless universe."""

        new = set()
        for x in universe:
            if x+1 not in universe: new.add(x)
            if x-1 not in universe: new.add(x); new.add(x-1)
        return new

    def show(universe, window, alive='■', dead=' ', space=' '):
        """Prints a segment of the universe on the screen."""

        print(space.join(alive if x in universe else dead for x in range(*window)))
```

**Example:**

```python
    universe   = {-1}       # A set containing the indices of living cells
    window     = (-40, 0)   # The segment of the universe that will be shown
    iterations = 40         # Number of iterations that will be shown
    
    for i in range(iterations):
        show(universe, window)
        universe = Rule110(universe)
```

**Output:**

                                                                                  ■
                                                                                ■ ■
                                                                              ■ ■ ■
                                                                            ■ ■   ■
                                                                          ■ ■ ■ ■ ■
                                                                        ■ ■       ■
                                                                      ■ ■ ■     ■ ■
                                                                    ■ ■   ■   ■ ■ ■
                                                                  ■ ■ ■ ■ ■ ■ ■   ■
                                                                ■ ■           ■ ■ ■
                                                              ■ ■ ■         ■ ■   ■
                                                            ■ ■   ■       ■ ■ ■ ■ ■
                                                          ■ ■ ■ ■ ■     ■ ■       ■
                                                        ■ ■       ■   ■ ■ ■     ■ ■
                                                      ■ ■ ■     ■ ■ ■ ■   ■   ■ ■ ■
                                                    ■ ■   ■   ■ ■     ■ ■ ■ ■ ■   ■
                                                  ■ ■ ■ ■ ■ ■ ■ ■   ■ ■       ■ ■ ■
                                                ■ ■             ■ ■ ■ ■     ■ ■   ■
                                              ■ ■ ■           ■ ■     ■   ■ ■ ■ ■ ■
                                            ■ ■   ■         ■ ■ ■   ■ ■ ■ ■       ■
                                          ■ ■ ■ ■ ■       ■ ■   ■ ■ ■     ■     ■ ■
                                        ■ ■       ■     ■ ■ ■ ■ ■   ■   ■ ■   ■ ■ ■
                                      ■ ■ ■     ■ ■   ■ ■       ■ ■ ■ ■ ■ ■ ■ ■   ■
                                    ■ ■   ■   ■ ■ ■ ■ ■ ■     ■ ■             ■ ■ ■
                                  ■ ■ ■ ■ ■ ■ ■         ■   ■ ■ ■           ■ ■   ■
                                ■ ■           ■       ■ ■ ■ ■   ■         ■ ■ ■ ■ ■
                              ■ ■ ■         ■ ■     ■ ■     ■ ■ ■       ■ ■       ■
                            ■ ■   ■       ■ ■ ■   ■ ■ ■   ■ ■   ■     ■ ■ ■     ■ ■
                          ■ ■ ■ ■ ■     ■ ■   ■ ■ ■   ■ ■ ■ ■ ■ ■   ■ ■   ■   ■ ■ ■
                        ■ ■       ■   ■ ■ ■ ■ ■   ■ ■ ■         ■ ■ ■ ■ ■ ■ ■ ■   ■
                      ■ ■ ■     ■ ■ ■ ■       ■ ■ ■   ■       ■ ■             ■ ■ ■
                    ■ ■   ■   ■ ■     ■     ■ ■   ■ ■ ■     ■ ■ ■           ■ ■   ■
                  ■ ■ ■ ■ ■ ■ ■ ■   ■ ■   ■ ■ ■ ■ ■   ■   ■ ■   ■         ■ ■ ■ ■ ■
                ■ ■             ■ ■ ■ ■ ■ ■       ■ ■ ■ ■ ■ ■ ■ ■       ■ ■       ■
              ■ ■ ■           ■ ■         ■     ■ ■             ■     ■ ■ ■     ■ ■
            ■ ■   ■         ■ ■ ■       ■ ■   ■ ■ ■           ■ ■   ■ ■   ■   ■ ■ ■
          ■ ■ ■ ■ ■       ■ ■   ■     ■ ■ ■ ■ ■   ■         ■ ■ ■ ■ ■ ■ ■ ■ ■ ■   ■
        ■ ■       ■     ■ ■ ■ ■ ■   ■ ■       ■ ■ ■       ■ ■                 ■ ■ ■
      ■ ■ ■     ■ ■   ■ ■       ■ ■ ■ ■     ■ ■   ■     ■ ■ ■               ■ ■   ■
    ■ ■   ■   ■ ■ ■ ■ ■ ■     ■ ■     ■   ■ ■ ■ ■ ■   ■ ■   ■             ■ ■ ■ ■ ■

