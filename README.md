# KoboldCPP + SillyTavern Docker Setup / 도커 설정

[English](#english) | [한국어](#korean)

---

<a name="english"></a>
## 🇺🇸 English

This project uses Docker Compose to set up a local LLM environment using [KoboldCPP](https://github.com/LostRuins/koboldcpp) backend and [SillyTavern](https://github.com/SillyTavern/SillyTavern) frontend.

### Prerequisites
*   **Docker & Docker Compose**
*   **NVIDIA GPU** & **NVIDIA Container Toolkit**

### Setup Instructions

1.  **Environment Setup**:
    Copy `.env.example` to `.env` and configure it.
    ```bash
    cp .env.example .env
    ```
    *   `MODEL_FILENAME`: Name of your `.gguf` file.
    *   `KOBOLD_GPU_LAYERS`: `-1` for full GPU offloading.

2.  **Download Model**:
    Place your `.gguf` model file in the `models/` directory.

3.  **Run**:
    ```bash
    docker compose up -d
    ```

4.  **Access**:
    *   **SillyTavern**: [http://localhost:8000](http://localhost:8000)
    *   API URL: `http://koboldcpp:5001`

---

<a name="korean"></a>
## 🇰🇷 한국어

이 프로젝트는 Docker Compose를 사용하여 [KoboldCPP](https://github.com/LostRuins/koboldcpp) 백엔드와 [SillyTavern](https://github.com/SillyTavern/SillyTavern) 프론트엔드 환경을 구축합니다.

### 필수 조건
*   **Docker 및 Docker Compose**
*   **NVIDIA GPU** 및 **NVIDIA Container Toolkit**

### 설정 방법

1.  **환경 설정**:
    `.env.example` 파일을 복사하여 `.env` 파일을 생성하고 설정을 수정합니다.
    ```bash
    cp .env.example .env
    ```
    *   `MODEL_FILENAME`: 다운로드한 `.gguf` 모델 파일의 이름과 정확히 일치해야 합니다.
    *   `KOBOLD_GPU_LAYERS`: GPU를 최대로 사용하려면 `-1`로 설정하세요.

2.  **모델 준비**:
    `models/` 폴더 안에 사용할 `.gguf` 모델 파일을 넣어주세요.

3.  **실행**:
    다음 명령어로 서비스를 시작합니다.
    ```bash
    docker compose up -d
    ```

4.  **접속**:
    *   **SillyTavern**: [http://localhost:8000](http://localhost:8000)
    *   **연결 설정**: SillyTavern에서 API 주소를 물어보면 `http://koboldcpp:5001` 을 입력하세요.
