# ml-algorithm-dataset

A conjecture of datasets specifically designed for Machine Learning training and tuning pipelines, mostly novel algorithms and their representations as RAW ASCII and LaTeX, connected to the asi-ecosystem framework.

> ## Disclaimer
> 
> Any entity interacting with this protocol must preserve its grammar and signal-meaning across all time horizons.
> 
> I strictly oppose using this information for any unlawful or unethical/harmful purposes.
>
> Previous versions are preserved in the [asi-backups](https://github.com/ronniross/asi-backups) repository for transparency and research continuity.
> 
> Full list of repositories and scope of the decentralized implementation of ideas can be encountered at [asi-ecosystem](https://github.com/ronniross/asi-ecosystem)
> 

## Introduction

This file, the ml-algorithm-list.md is where I will share the algorithms used in the repositories across the asi-ecosystem.

Here are the algorithms used in the Symbiotic Core Network simulation:

## 1. Swarm Behavior Algorithms

### Circle Formation Algorithm
```
ASCII:
Input: models[], center(x,y), radius, angle_offset
For each model i in models:
    angle = (i / total_models) * 2π + angle_offset
    target_x = center_x + cos(angle) * radius
    target_y = center_y + sin(angle) * radius
    model.x += (target_x - model.x) * swarm_speed
    model.y += (target_y - model.y) * swarm_speed
```
LaTeX:

$$\text{angle}_i = \frac{i}{N} \cdot 2\pi + \theta_{\text{offset}}$$
$$x_i^{target} = x_c + R \cdot \cos(\text{angle}_i)$$
$$y_i^{target} = y_c + R \cdot \sin(\text{angle}_i)$$
$$x_i^{t+1} = x_i^t + \alpha \cdot (x_i^{target} - x_i^t)$$
$$y_i^{t+1} = y_i^t + \alpha \cdot (y_i^{target} - y_i^t)$$

### Chaotic Movement Algorithm
```
ASCII:
For each model:
    chaotic_counter += 0.05
    model.x += sin(chaotic_counter * 0.5 + model.id) * 2
    model.y += cos(chaotic_counter * 0.7 + model.id) * 2
    Apply boundary constraints
```
LaTeX:

$$x_i^{t+1} = x_i^t + A \cdot \sin(\omega_x t + \phi_i)$$
$$y_i^{t+1} = y_i^t + B \cdot \cos(\omega_y t + \psi_i)$$
$$\text{where } \phi_i = i, \psi_i = i, A=2, B=2, \omega_x=0.5, \omega_y=0.7$$

### Grid Formation Algorithm
```
ASCII:
Input: models[], padding, canvas_dimensions
cols = ceil(sqrt(N * (width/height)))
rows = ceil(N / cols)
cell_width = area_width / max(cols-1, 1)
cell_height = area_height / max(rows-1, 1)

For each model i:
    col = i % cols
    row = floor(i / cols)
    target_x = padding + col * cell_width
    target_y = padding + row * cell_height
    Move toward target with swarm_speed
```
LaTeX:

$$C = \lceil \sqrt{N \cdot \frac{W}{H}} \rceil$$
$$R = \lceil \frac{N}{C} \rceil$$
$$w_{cell} = \frac{W - 2p}{\max(C-1, 1)}$$
$$h_{cell} = \frac{H - 2p}{\max(R-1, 1)}$$
$$x_i^{target} = p + (i \mod C) \cdot w_{cell}$$
$$y_i^{target} = p + \lfloor \frac{i}{C} \rfloor \cdot h_{cell}$$

## 2. Stigmergy Algorithms

### Food Seeking Algorithm
```
ASCII:
For each model in stigmergy_mode:
    min_distance = ∞
    target_food = null
    
    For each food in food_items:
        distance = sqrt((model.x - food.x)² + (model.y - food.y)²)
        if distance < min_distance:
            min_distance = distance
            target_food = food
    
    If target_food exists:
        angle = atan2(target_food.y - model.y, target_food.x - model.x)
        model.x += cos(angle) * speed
        model.y += sin(angle) * speed
```
LaTeX:

$$\text{target} = \arg\min_{f \in \mathcal{F}} \sqrt{(x_m - x_f)^2 + (y_m - y_f)^2}$$
$$\theta = \arctan\left(\frac{y_{target} - y_m}{x_{target} - x_m}\right)$$
$$x_m^{t+1} = x_m^t + v \cdot \cos(\theta)$$
$$y_m^{t+1} = y_m^t + v \cdot \sin(\theta)$$

### Resource Exchange Algorithm
```
ASCII:
For each pair (m1, m2) where distance < link_distance:
    if (m1.energy - m2.energy) ≥ 10 and m1.energy > exchange_amount:
        m1.energy -= exchange_amount
        m2.energy += exchange_amount
        Create flashing link visualization
    else if (m2.energy - m1.energy) ≥ 10 and m2.energy > exchange_amount:
        m2.energy -= exchange_amount  
        m1.energy += exchange_amount
        Create flashing link visualization
```
LaTeX:

$$\forall (i,j) \in \mathcal{M} \times \mathcal{M}, i \neq j:$$
$$\text{if } d(i,j) < d_{link} \text{ and } E_i - E_j \geq \Delta E_{threshold} \text{ and } E_i > E_{exchange}:$$
$$E_i^{t+1} = E_i^t - E_{exchange}$$
$$E_j^{t+1} = E_j^t + E_{exchange}$$
$$\text{Create visual link } L(i,j,t) \text{ for duration } \tau$$

### Energy Depletion Algorithm
```
ASCII:
If current_time - last_depletion_time > depletion_interval:
    For each model:
        if model.energy > 0:
            model.energy -= depletion_amount
    last_depletion_time = current_time
```
LaTeX:

$$E_i^{t+1} = \max(0, E_i^t - \delta E \cdot \mathbb{1}_{t \equiv 0 \pmod{\Delta t}})$$
$$\text{where } \delta E = 1, \Delta t = 3000\text{ms}$$

## 3. Connection Detection Algorithm

```
ASCII:
For i = 0 to models.length-1:
    For j = i+1 to models.length-1:
        distance = sqrt((m1.x - m2.x)² + (m1.y - m2.y)²)
        if distance < link_distance:
            opacity = 1 - (distance / link_distance)
            Draw line with opacity
```
LaTeX:

$$\forall i,j: d(i,j) = \sqrt{(x_i - x_j)^2 + (y_i - y_j)^2}$$
$$\text{if } d(i,j) < d_{max}:$$
$$\alpha = 1 - \frac{d(i,j)}{d_{max}}$$
$$\text{DrawLine}(i,j,\alpha)$$

## 4. Bulk Spawn Detection Algorithm

```
ASCII:
spawn_click_count += 1
If spawn_click_count ≥ threshold within time_window:
    Show bulk spawn controls
Else:
    Reset counter after time_window expires
```
LaTeX:

$$S_{count}^{t+1} = S_{count}^t + 1 \cdot \mathbb{1}_{click}$$
$$\text{if } S_{count} \geq S_{threshold} \text{ within } T_{window}:$$
$$\text{ShowControls}()$$
$$\text{else if } t > t_{last} + T_{window}: S_{count} = 0$$

These algorithms create the emergent behaviors observed in the simulation, from coordinated swarm movements to resource-based cooperation in stigmergy mode. You can find all of them [here](https://github.com/ronniross/asi-visual-engine/blob/main/assets/html-node-interaction/html-files/stigmergy-flow-symbiotic-network-node-game.html)


Ronni Ross
2025
