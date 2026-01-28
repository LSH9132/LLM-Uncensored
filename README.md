# KoboldCPP + SillyTavern Docker Setup / 도커 설정

[English](#english) | [한국어](#korean)

---

<a name="english"></a>
## 🇺🇸 English

This project uses Docker Compose to set up a local LLM environment using [KoboldCPP](https://github.com/LostRuins/koboldcpp) backend and [SillyTavern](https://github.com/SillyTavern/SillyTavern) frontend.

### Prerequisites
*   **Docker & Docker Compose**
*   **NVIDIA GPU** & **NVIDIA Container Toolkit**
*   **Tailscale Auth Key**: [Generate Key](https://login.tailscale.com/admin/settings/keys)

### Setup Instructions

1.  **Environment Setup**:
    Copy `.env.example` to `.env` and configure it.
    ```bash
    cp .env.example .env
    ```
    *   `MODEL_FILENAME`: Name of your `.gguf` file.
    *   `KOBOLD_GPU_LAYERS`: `-1` for full GPU offloading.
    *   `TS_AUTHKEY`: **Required**. Paste your Tailscale key here.

2.  **Download Model**:
    Place your `.gguf` model file in the `models/` directory.

3.  **Run**:
    ```bash
    docker compose up -d
    ```

4.  **Access**:
    *   Unlike the previous setup, ports are **not exposed locally**.
    *   Access via your Tailscale IP: `http://<tailscale-ip>:8000`
    *   **SillyTavern Connection**: Use `http://localhost:5001` (since they share the network namespace).

---

<a name="korean"></a>
## 🇰🇷 한국어

이 프로젝트는 Docker Compose를 사용하여 [KoboldCPP](https://github.com/LostRuins/koboldcpp) 백엔드와 [SillyTavern](https://github.com/SillyTavern/SillyTavern) 프론트엔드 환경을 구축합니다.
**Tailscale**을 통해 외부 인터넷 연결 없이 안전한 VPN 네트워크로만 통신합니다.

### 필수 조건
*   **Docker 및 Docker Compose**
*   **NVIDIA GPU** 및 **NVIDIA Container Toolkit**
*   **Tailscale Auth Key**: [키 생성하기](https://login.tailscale.com/admin/settings/keys)

### 설정 방법

1.  **환경 설정**:
    `.env.example` 파일을 복사하여 `.env` 파일을 생성하고 설정을 수정합니다.
    ```bash
    cp .env.example .env
    ```
    *   `MODEL_FILENAME`: 다운로드한 `.gguf` 모델 파일의 이름.
    *   `KOBOLD_GPU_LAYERS`: GPU 최대 사용 시 `-1`.
    *   `TS_AUTHKEY`: **필수**. 발급받은 Tailscale 인증 키를 붙여넣으세요.

2.  **모델 준비**:
    `models/` 폴더 안에 `.gguf` 파일 위치.

3.  **실행**:
    ```bash
    docker compose up -d
    ```

4.  **접속**:
    *   로컬 포트(localhost:8000)는 더 이상 열리지 않습니다.
    *   Tailscale IP를 통해 다른 기기에서 접속하세요: `http://<tailscale-ip>:8000`
    *   **SillyTavern 설정**: API 주소를 `http://localhost:5001`로 설정하세요. (컨테이너끼리 네트워크를 공유합니다)
