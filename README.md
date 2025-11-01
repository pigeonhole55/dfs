# Delta Force Heli 101 - Stinger Missile Simulation

Real-time Stinger missile engagement simulation with D/2 evasion maneuver using advanced Proportional Navigation (PN) guidance.

## Features

- Realistic physics simulation
- Advanced Proportional Navigation guidance for the missile
- D/2 evasion maneuver demonstration
- Beautiful canvas-based visualization
- Slow-motion replay capability

## Tech Stack

- React 18
- TypeScript
- Vite
- Canvas API

## Getting Started

### Install Dependencies

```bash
npm install
```

### Development

```bash
npm run dev
```

### Build

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## Deployment

This project can be deployed to:

1. **Azure Static Web Apps** (Free for students) - See [DEPLOY.md](./DEPLOY.md)
2. **Vercel** - Just connect your GitHub repo to Vercel

### Quick Deploy to Vercel

1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import your GitHub repository
4. Vercel will auto-detect Vite and deploy!

### Deploy to Azure

See the detailed guide in [DEPLOY.md](./DEPLOY.md)

## Physics Parameters

- Initial Distance (D): 1000m
- Missile Speed (V_m): 300 km/h
- Helicopter Speed (V_t): 70 km/h
- Maximum Acceleration: 84 m/s² (8.6g)
- PN Constant (N): 3.5

## License

MIT

