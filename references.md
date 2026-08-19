# Tài liệu tham khảo — Đề tài GitOps/ArgoCD

## Ngày 1 — Kubernetes cơ bản
- K3s Documentation. (n.d.). Truy cập ngày 14/08/2026, từ https://docs.k3s.io/
- TechWorld with Nana. Kubernetes Tutorial for Beginners [Video]. YouTube.
- Kubernetes Documentation. (n.d.). Concepts. Truy cập ngày 14/08/2026, từ https://kubernetes.io/docs/concepts/

## Ngày 2 — ArgoCD Example Apps — Guestbook
https://github.com/argoproj/argocd-example-apps

## Ngày 3 (= Ngày 7 cũ) — Kustomize
- Kustomize Official Documentation
  https://kubectl.docs.kubernetes.io/references/kustomize/
  → Tài liệu chính thức về cách viết kustomization.yaml, patch, base/overlay.
- Kubernetes Docs — Declarative Management with Kustomize
  https://kubernetes.io/docs/tasks/manage-kubernetes-objects/kustomization/
  → Hướng dẫn dùng Kustomize tích hợp sẵn trong kubectl.


## Ngày 4 (= Ngày 8 cũ) — Cài đặt ArgoCD
- ArgoCD Official Documentation — Getting Started
  https://argo-cd.readthedocs.io/en/stable/getting_started/
  → Tài liệu chính thức hướng dẫn cài đặt ArgoCD vào cluster Kubernetes.


## Ngày 5 
- ArgoCD Official Docs – Application Definition & Sync Policy
  https://argo-cd.readthedocs.io/en/stable/user-guide/application-set/
  Dùng để cấu hình Application trỏ tới repo GitHub (path overlays/dev) với sync policy Automatic, cho phép ArgoCD tự động phát hiện và đồng bộ khi Git thay đổi.

- ArgoCD Official Docs – Automated Sync Policy
  https://argo-cd.readthedocs.io/en/stable/user-guide/auto_sync/
  Giải thích cơ chế polling Git repo (mặc định mỗi 3 phút) và cách ArgoCD tự sync khi phát hiện commit mới, làm cơ sở cho demo auto-sync ở Ngày 5.

- ArgoCD Official Docs – Sync History and Rollback
  https://argo-cd.readthedocs.io/en/stable/user-guide/commands/argocd_app_history/
  Dùng để đối chiếu Sync Revision (commit hash) trong tab History and Rollback với commit trên GitHub, làm bằng chứng ArgoCD tự đồng bộ đúng thay đổi.


## Ngày 6

- **Nguồn:** Argo CD Docs – Automated Sync Policy (Self-Heal)
  **URL:** https://argo-cd.readthedocs.io/en/stable/user-guide/auto_sync/
  **Sử dụng:** Tham khảo cơ chế `selfHeal` — khi bật, Argo CD tự động sync lại sau self-heal timeout (mặc định 5 giây) nếu phát hiện trạng thái cluster lệch khỏi Git, dùng làm cơ sở lý thuyết cho phần demo self-healing ở tầng GitOps (xóa deployment → Argo CD tự phục hồi).

- **Nguồn:** Argo CD Docs – Core Concepts (Sync & Health status)
  **URL:** https://argo-cd.readthedocs.io/en/latest/core_concepts/
  **Sử dụng:** Tham khảo định nghĩa "Sync" (so sánh trạng thái Git với trạng thái live) và "Health" (ứng dụng có đang chạy đúng không), dùng để giải thích trạng thái OutOfSync → Synced khi chụp ảnh minh chứng.

- **Nguồn:** Git Docs – git-revert(1)
  **URL:** https://git-scm.com/docs/git-revert
  **Sử dụng:** Tham khảo cơ chế `git revert` — tạo commit mới để hoàn tác thay đổi của commit trước đó mà không xóa lịch sử, dùng làm cơ sở cho bước test rollback (sửa sai → revert → push → Argo CD tự đưa hệ thống về trạng thái cũ).

## Ngày 7 —


## Ngày 8 —


## Ngày 9 —
