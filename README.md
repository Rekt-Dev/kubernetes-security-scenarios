# Kubernetes Security Scenarios

Advanced threat scenario library for Kubernetes security engineering. Each scenario presents a realistic attack vector, a vulnerable baseline environment, and a step-by-step hardened resolution.

## Scenario Categories

| Category | Scenarios |
|---|---|
| Privilege Escalation | Container breakout, RBAC misconfiguration, hostPath abuse |
| Network Attacks | Pod-to-pod lateral movement, DNS spoofing, service exposure |
| Supply Chain | Compromised image, missing admission policy, unsigned workload |
| Secrets Leakage | Env var exposure, etcd plaintext secrets, over-permissive RBAC |
| Runtime Threats | Unexpected syscalls, privileged container detection, Falco evasion |
| Cluster Compromise | Kubeconfig theft, API server misconfiguration, etcd access |

## Scenario Format

Each scenario follows a consistent structure:

```
scenarios/
└── <scenario-name>/
    ├── README.md         # Attack description, impact, MITRE mapping
    ├── setup/            # Vulnerable baseline manifests
    ├── exploit/          # Reproduction steps
    └── remediation/      # Hardened configuration and verification
```

## Usage

```bash
# Deploy a scenario environment
kubectl apply -f scenarios/<name>/setup/

# Follow the README walkthrough
# Apply remediation
kubectl apply -f scenarios/<name>/remediation/

# Verify
bash scenarios/<name>/verify.sh
```

## Framework Alignment

Scenarios mapped to **MITRE ATT&CK for Containers** and **CKS exam objectives**.
