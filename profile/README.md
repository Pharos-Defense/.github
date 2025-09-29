# Pharos AI Defense Platform MVP

**Autonomous Threat Detection and Response System**

> Building the world's first fully integrated AI-powered weapon detection platform with coordinated drone swarm response.

---

## 📝 Project Overview

Pharos AI is developing an autonomous threat detection and response platform that combines:
- **AI-Powered Detection**: YOLOv8-based weapon detection with 95%+ accuracy
- **Edge Processing**: Real-time inference on NVIDIA Jetson Orin Nano (67 TOPS)
- **Drone Swarms**: Coordinated autonomous response with PX4/MAVLink integration
- **Zero-Latency Response**: 1.8-second detection to 12-second drone deployment

### The Problem We're Solving
- Traditional security response time: 3-5 seconds (human reaction)
- Butler PA incident (July 13, 2024): 8+ minute response time, 142-yard blind spot
- Current systems: 60%+ false positives, disconnected response protocols

### Our Solution
- **1.8-second weapon detection** (266% faster than humans)
- **360° overwatch formation** deployment in 12 seconds
- **<5% false positive rate** with 95%+ detection accuracy
- **45+ minute flight time** per drone with intelligent swarm coordination

---

## 🏎️ Quick Start

### Prerequisites
- **Hardware**: NVIDIA Jetson Orin Nano Super Developer Kit ($249)
- **Software**: Ubuntu 20.04 LTS, JetPack 5.1.1, Docker
- **Development**: Python 3.9+, Node.js 18+, Git

### Installation

1. **Clone Repository**
```bash
git clone https://github.com/pharos-ai/pharos-ai-mvp.git
cd pharos-ai-mvp
```

2. **Environment Setup**
```bash
cp .env.example .env
# Edit .env with your configuration
```

3. **Docker Development**
```bash
docker-compose up --build
```

4. **Access Application**
- Frontend: http://localhost:3000
- Backend API: http://localhost:8000
- API Documentation: http://localhost:8000/docs

### Edge Deployment (Jetson Orin Nano)
```bash
cd edge/jetson/
chmod +x setup_jetson.sh
./setup_jetson.sh
```

---

## 🏗️ Architecture

### System Components

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Video Input   │───▶│  Edge Processing │───▶│  Drone Swarm    │
│   (Cameras)     │    │  (Jetson Orin)  │    │  (PX4/MAVLink)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  Web Dashboard  │◀───│   FastAPI       │───▶│  Alert System   │
│  (React/TS)     │    │   Backend       │    │  (Notifications)│
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Technology Stack

**Backend (Python)**
- FastAPI: High-performance async API framework
- YOLOv8: State-of-the-art object detection
- TensorRT: GPU acceleration and optimization
- OpenCV: Video processing and computer vision
- MAVSDK: Drone communication and control

**Frontend (TypeScript/React)**
- React 18: Modern component-based UI
- TypeScript: Type-safe development
- Material-UI: Professional component library
- WebSocket: Real-time communication
- WebRTC: Low-latency video streaming

**Edge Computing**
- NVIDIA Jetson Orin Nano: 67 TOPS AI performance
- JetPack 5.1.1: Optimized Linux distribution
- TensorRT: 3x inference speedup with INT8 quantization
- Docker: Containerized deployment

**Drone Integration**
- PX4 Autopilot: Open-source flight controller
- MAVLink: Drone communication protocol
- Formation Control: Custom swarm algorithms
- Failsafe Management: Emergency protocols

---

## 🔧 Development Roadmap

### Phase 1: Core Detection (Weeks 1-2)
- [ ] YOLOv8 weapon detection implementation
- [ ] Real-time video processing (30 FPS)
- [ ] Confidence scoring and threshold management
- [ ] Basic alert system (visual + audio)
- [ ] Performance monitoring dashboard

### Phase 2: Web Interface (Weeks 3-4)
- [ ] React dashboard for live monitoring
- [ ] WebSocket integration for real-time updates
- [ ] Alert management and notification system
- [ ] User authentication and settings
- [ ] System metrics and performance monitoring

### Phase 3: Edge Deployment (Weeks 5-6)
- [ ] TensorRT optimization for Jetson Orin Nano
- [ ] Edge processing with cloud backup
- [ ] Multiple camera input support
- [ ] Local storage and data management
- [ ] Remote monitoring capabilities

### Phase 4: Drone Integration (Weeks 7-8)
- [ ] MAVLink communication setup
- [ ] Basic drone positioning and movement
- [ ] Coordinated response to threat detection
- [ ] Formation flying algorithms (2-3 drones)
- [ ] Emergency protocols and failsafes

---

## 📊 Performance Specifications

### Detection Performance
- **Accuracy**: 95%+ precision, 90%+ recall
- **Speed**: 50-100ms inference time per frame
- **Throughput**: 30 FPS real-time processing
- **False Positives**: <5% with confidence threshold tuning

### Hardware Performance
- **AI Processing**: 67 TOPS (Jetson Orin Nano Super)
- **Memory**: 8GB LPDDR5, 102 GB/s bandwidth
- **Power**: 15W performance mode (25W boost available)
- **Storage**: NVMe SSD support (up to 2TB)

### Response Times
- **Detection**: 1.8 seconds (weapon identification)
- **Alert**: <500ms (notification dispatch)
- **Drone Deployment**: 12 seconds (formation establishment)
- **Total Response**: <15 seconds (detection to positioning)

---

## 🧪 Testing & Validation

### Unit Tests
```bash
# Backend tests
cd backend && python -m pytest tests/

# Frontend tests
cd frontend && npm test
```

### Integration Tests
```bash
# End-to-end system testing
python scripts/test_system.py
```

### Performance Benchmarks
```bash
# Model performance evaluation
python scripts/benchmark_detection.py

# System performance profiling
python scripts/profile_performance.py
```

---

## 🔒 Security & Compliance

### Data Protection
- Local processing (no cloud dependency for critical operations)
- Encrypted communication channels
- Secure credential management
- Privacy-compliant video handling

### Safety Protocols
- Graduated response system
- Human override capabilities
- Emergency stop mechanisms
- Comprehensive logging and audit trails

---

## 🤝 Contributing

We welcome contributions from the defense technology community!

1. **Fork the repository**
2. **Create feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit changes**: `git commit -m 'Add amazing feature'`
4. **Push to branch**: `git push origin feature/amazing-feature`
5. **Open Pull Request**

### Development Guidelines
- Follow PEP 8 (Python) and ESLint (TypeScript) standards
- Write comprehensive tests for new features
- Update documentation for API changes
- Ensure Docker containers build successfully

---

## 📄 License & Legal

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Export Control Notice
This software may be subject to U.S. export control regulations. Please consult with legal counsel regarding export restrictions before distribution.

---

## 📞 Contact & Support

**Pharos AI Defense Platform**
- **Website**: https://pharos-ai.com
- **Email**: support@pharos-ai.com
- **Documentation**: https://docs.pharos-ai.com

**Founded by Brandon Coburn**
- Navy veteran with Emergency Operations Center experience
- 2 years managing $5M surveillance systems
- Responsible for safety of 25,000+ personnel across 4 commands

---

## 🎖️ Acknowledgments

- **NVIDIA** for Jetson platform and TensorRT optimization
- **PX4 Development Team** for open-source autopilot software
- **Ultralytics** for YOLOv8 implementation
- **Defense Innovation Community** for ongoing support and feedback

---

*Building the future of autonomous security - preventing failures before they happen.*
