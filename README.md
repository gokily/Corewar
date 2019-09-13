# Corewar


This project was made in collaboration with [ratin](https://github.com/ratin42), [hlombard](https://github.com/HugotOwned) and [gly](https://github.com/gokily).

The goal of this project is to create a virtual machine in which champions will fight against one another, but also to create an assembler to compile those champions as well as a champion.

### What is Corewar?
* Corewar is a game that brings champions together around a virtual machine, with the objective being for these champions to stay alive.
* The champion has a set of instructions run when the game start. You can find the champion in each `.s` file.
* The assembler will compile a champion into a byte code that will be stored in a `.cor` file.
* The virtual machine then run the game by :
  - receiving `.cor` files;
  - placing each champion in the arena (memory);
  - reading the byte codes of each champion, interpreting and running them if they're valid.
* The game ends when all the processes are dead. The winner is the last player reported to be alive.

### Bonus
* Decompiler
* Man page
* Ncurses output
* flag v, a, stealth

### Usage
* Run the Makefile to create the `asm` and `corewar` executable files
```
make
```
* To use the Assembler
```
./asm <file_name.s>
```
* To use the Virtual Machine
```
./corewar [-n N] [-dump N] [-v N] [-visu] [--stealth] [-a] <file_name.cor> ...
```
  - flag n - Assign order N to next champion, default is : first champ is first to play;
  - flag dump - Dumps memory after N cycles then exits;
  - flag v - Verbosity levels, can be added together to enable several
    - 0 : Show only essentials
    - 1 : Show lives
    - 2 : Show cycles
    - 4 : Show operations (Params are NOT litteral ...)
    - 8 : Show deaths
    - 16 : Show PC movements (Except for jumps);
  - flag visu - Ncurses output mode;
  - flag stealth - Competition mode, hide code with visual;
  - flag a - Prints output from "aff".
* To use the Decompiler
```
./disassembler <file_name.cor>
```
* To use the Man page
```
man ./corewar.man
```

### Contributions
* [ratin](https://github.com/ratin42)
  - Assembler
  - Decompiler
* [hlombard](https://github.com/HugotOwned)
  - Virtual Machine
  - Ncurses output
* [gly](https://github.com/gokily).
  - Virtual Machine
  - Verbosity flag
* [syzhang](https://github.com/syzhang16)
  - Virtual Machine
  - Champion
  - Man page
