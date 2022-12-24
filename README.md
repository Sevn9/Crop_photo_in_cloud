# Crop_photo_in_cloud

## 1. Используемые сервисные аккаунты
**vvot-30-face-detection-function-serverless**:
- ai.vision.user
- ymq.writer
- storage.viewer

**vvot-30-face-detection-function-serverless**:
- serverless.function.invoker

**vvot-30-face-cut-container**:
- storage.viewer
- storage.uploader
- ydb.editor
- container-registry.images.puller

**vvot-30-face-cut-trigger**:
- ymq.reader
- serverless.containers.invoker

**vvot30-boot-function-serverless**:
- ydb.viewer
- ydb.editor

## 2. Объекты
### Бакеты
- itis-2022-2023-vvot30-photos
- itis-2022-2023-vvot30-faces
### БД
- vvot30-db-photo-face
### Очереди
- vvot30-tasks
### api-gateway:
- itis-2022-2023-vvot30-api
### Триггеры
- vvot30-photo-trigger (сервисный аакаунт **vvot-30-face-detection-function-serverless**)
- vvot30-task-trigger (сервисный аккаунт **vvot-30-face-cut-trigger**)
### Функции
- vvot30-face-detection (сервисный аккаунт **vvot-30-face-detection-function-serverless**, код из файла **vvot30-face-detection.py**)
- vvot30-boot (сервисный аккаунт **vvot30-boot-function-serverless**, код из файла **vvot30-boot.py**)
### Контейнер
- vvot30-face-cut (сервисный аккаунт **vvot-30-face-cut-container**, код из файла **face-cut.py**)
