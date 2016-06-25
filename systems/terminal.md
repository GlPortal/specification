# Terminal
Pops up when you hit F2.
## Terminal and the ECS
How does the terminal fit into the ECS? 
### Components
- **Line Buffer** Holds the previous lines 
- **Char Buffer** Holds the current input
- **Buffer Position** The current position in the char buffer

### System
The terminal system acts on all the components of the terminal entity.
## Commands
- exit
