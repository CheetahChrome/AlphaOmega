---
layout: default
title: Pulumi
---  
  
| Action                                         | Command(s)                        | Description                                               |
|-----------------------------------------------|------------------------------------|-----------------------------------------------------------|
| **Pulumi Login**                               | `pulumi login`                    | Logs in to Pulumi.                                        |
| **New Project**                                | `pulumi new`                      | Creates a new project based on language in the CWD.       |
| **View State**                                 | `pulumi stack`                    | Manages and views the state of the stack.                 |
| **Dest Organization**                         | `pulumi org set-default {Name}`   | Sets the default destination organization for operations. |
| **View Backend/Current Stack/Pending Operations** | `pulumi about`                   | Displays backend, current stack, and pending operations.  |
| **Destroy**                                    | `pulumi destroy`, `pulumi stack rm` | Removes the stack and its history.                        |
| **Up**                                        | `pulumi up --yes`                 | Deploys changes with overrides (`--yes`).                 |
| **Cancel**                                     | `pulumi cancel`                   | Cancels an ongoing `pulumi up`.                           |
