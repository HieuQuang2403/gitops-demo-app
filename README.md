# GitOps Demo - ArgoCD + K3s + Kustomize

## Mục tiêu
Triển khai mô hình GitOps quản lý ứng dụng trên Kubernetes, sử dụng ArgoCD
để tự động đồng bộ, tự phục hồi (self-healing) và rollback khi có lỗi.

## Kiến trúc
Dev sửa YAML → push GitHub → ArgoCD phát hiện thay đổi → tự động sync → K3s cập nhật

## Ứng dụng
Sử dụng ArgoCD guestbook sample app (không tự viết Dockerfile) để tập trung
vào tầng GitOps thay vì độ phức tạp ứng dụng.

## Cấu trúc thư mục

```
gitops-demo-app/
├── base/              # cấu hình gốc
├── overlays/
│   ├── dev/           # môi trường dev
│   └── prod/          # môi trường prod
└── docs/evidence/     # ảnh/video minh chứng
```

## Cách chạy lại
```bash
kubectl apply -k overlays/dev
```

## Minh chứng
- Self-healing: xem docs/evidence/self-healing.png
- Rollback: xem docs/evidence/rollback.png
- Video demo: [link sẽ cập nhật]

## Tài liệu tham khảo
Xem file references.md