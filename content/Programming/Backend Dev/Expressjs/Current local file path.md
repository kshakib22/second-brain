The following lines of code gives the directory name and saves it in the variable `__dirname`. In older JS this was a variable itself as a **global variable**. That's why to maintain convention, the double underscores are used in front of the name.
```node
import { dirname } from "path";
import { fileURLToPath } from "url";
const __dirname = dirname(fileURLToPath(import.meta.url));
```