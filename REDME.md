# Interactive Bézier Curve with Physics (Web)

## Objective
This project implements an interactive cubic Bézier curve that behaves like a rope.
The curve dynamically responds to real-time mouse input and uses a spring–damping
physics model for smooth, natural motion.

The project demonstrates understanding of:
- Bézier curve mathematics
- Tangent computation
- Basic physics simulation
- Real-time rendering and interaction

---

## Technologies Used
- HTML5
- JavaScript (Vanilla)
- HTML Canvas API

No external libraries or prebuilt Bézier/physics APIs are used.

---

## Bézier Curve Mathematics
A cubic Bézier curve is defined using four control points:

B(t) = (1 − t)³P₀ + 3(1 − t)²tP₁ + 3(1 − t)t²P₂ + t³P₃ ,  where t ∈ [0,1]

The curve is rendered by sampling values of t at small intervals (Δt = 0.01).

---

## Tangent Computation
The tangent vector at any point on the curve is computed using the derivative:

B′(t) = 3(1 − t)²(P₁ − P₀)
      + 6(1 − t)t(P₂ − P₁)
      + 3t²(P₃ − P₂)

Tangents are normalized and drawn as short line segments along the curve.

---

## Physics Model (Spring–Damping)
The middle control points follow a spring–damping system:

acceleration = −k(position − target) − damping × velocity

Where:
- k is the spring stiffness
- damping reduces oscillations
- velocity and position are updated manually each frame

This produces a rope-like, smooth motion.

---

## Interaction
- Endpoints (P₀ and P₃) are fixed.
- Control points (P₁ and P₂) move in response to mouse movement.
- Motion is continuous and real-time.

---

## Rendering
- HTML Canvas is used for rendering
- requestAnimationFrame ensures ~60 FPS
- The scene includes:
  - Bézier curve
  - Control points
  - Tangent vectors
  - Animated particle background

---

## Constraints Followed
- No UIBezierPath, SVG paths, or canvas Bézier helpers
- No physics engines or animation libraries
- All math and physics implemented manually

---

## How to Run
1. Open `index.html` in any modern browser
2. Move the mouse to interact with the rope
3. Observe smooth spring motion and tangents
