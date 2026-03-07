# ALICE-Robotics

Robot control & trajectory planning platform with real-time kinematics

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-kinematics, alice-physics, alice-rtos, alice-edge, alice-bridge

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/trajectory` | 軌道計画（逆運動学） |
| `POST` | `/api/v1/simulate` | 物理シミュレーション実行 |
| `POST` | `/api/v1/deploy` | エッジデバイスへデプロイ |
| `GET ` | `/api/v1/robots` | ロボット一覧・ステータス |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
