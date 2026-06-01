BPF subsystem

| Option                                                                 | Valeur       | Description                                                                                                     |
|------------------------------------------------------------------------|--------------|-----------------------------------------------------------------------------------------------------------------|
| Enable bpf() system call                                               | activé       | Autorise l'utilisation de la syscall bpf() pour exécuter des programmes BPF.                                    |
| Enable BPF Just In Time compiler                                       | activé       | Active le compilateur JIT pour optimiser les programmes BPF en temps réel.                                      |
| Permanently enable BPF JIT and remove BPF interpreter                  | désactivé    | Permet l'exécution directe des programmes BPF sans interprète, si activé.                                       |
| Disable unprivileged BPF by default                                    | activé       | Désactive les privilèges requis pour exécuter des programmes BPF par défaut.                                    |
| Preload BPF file system with kernel specific program and map iterators | désactivé    | Charge le système de fichiers BPF avec des programmes spécifiques et itérateurs de mappage du noyau, si activé. |
| Enable BPF LSM Instrumentation                                         | activé       | Intègre l'Instrumentation BPF dans le Système de Maîtrise du Ligaturenement (LSM).                              |
