# Kevin M. Hernandez

U.S. Marine Corps Corporal moving into **platform engineering**. I build and test
secure delivery paths for software on Kubernetes, with a focus on disconnected
(air-gapped) environments. Available for a **DoD SkillBridge** internship
starting December 2026. Bilingual: English and Spanish.

## What I'm building

**[airgap-exploration](https://github.com/km-hernandez/airgap-exploration)**:
one small service, carried along the path software takes in the DoD. Each step
has a one-command proof that fails if a control does not hold.

| Step | Proof |
| --- | --- |
| Kubernetes runtime | `make k3d-validate`: non-root, no capabilities, read-only root filesystem, and default-deny NetworkPolicy tested in both directions |
| Disconnected-style delivery | `make zarf-validate`: a versioned Zarf package deployed to a fresh cluster, with every image served from the in-cluster registry |
| Platform integration | `make uds-validate`: a UDS `Package` CR on UDS Core, with operator-generated policies, Istio ambient identity authorization, and ingress through the tenant gateway |
| CI gates | pytest, Bandit, pip-audit, Trivy, kubeconform, and a custom secret scanner on every pull request |

While testing on UDS Core I found that relabeling an already-connected pod does
not cut it off in Istio ambient mode, so the lab now authorizes ServiceAccount
identity and tests each layer with fresh pods.

## Tools I use

Kubernetes · k3d · Kustomize · Zarf · UDS CLI and UDS Core · Istio · Docker ·
GitHub Actions · Python and FastAPI · Trivy

## Next

- Signed images and Zarf packages, verified before deployment
- CompTIA Security+ (in preparation)
- Terraform on AWS
