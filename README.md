# SmartDisk — Dynamic Disk Scheduling Simulator

An interactive web-based simulator that demonstrates disk scheduling algorithms used in Operating Systems. SmartDisk helps students understand disk head movement, request waiting time, estimated seek time, and scheduling performance through visual comparisons.

## 📌 Project Overview

In an operating system, multiple processes may request disk input/output operations. Disk scheduling algorithms determine the order in which these requests are serviced.

SmartDisk simulates and compares four disk scheduling algorithms:

- **FCFS** — First Come, First Served
- **SSTF** — Shortest Seek Time First
- **SCAN** — Elevator Algorithm
- **C-SCAN** — Circular SCAN

The application provides a web interface where users can configure disk parameters, run simulations, and compare algorithm results.

## 🎯 Objectives

- Understand disk scheduling algorithms practically.
- Visualize disk head movement across cylinders.
- Compare total head movement and waiting time.
- Simulate requests arriving at different times.
- Demonstrate the trade-offs between different scheduling strategies.
- Support learning through an interactive web application.

## ✨ Features

- Four disk scheduling algorithms.
- Configurable disk size and initial head position.
- Configurable head movement direction.
- Dynamic request-arrival simulation.
- Visualization of disk head movement.
- Comparison of scheduling performance metrics.
- Request-by-request results.
- Input validation and automated tests.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Scheduling algorithms and simulation logic |
| Flask | Backend web framework and API |
| HTML5 | Web page structure |
| CSS3 | User interface styling |
| JavaScript | Frontend interactions |
| Chart.js | Charts and data visualization, if enabled in the interface |
| JSON | Communication between frontend and backend |
| unittest | Automated testing |

## 📂 Project Structure

```text
SmartDisk_Final/
├── app.py
├── requirements.txt
├── README.md
├── scheduler/
│   └── algorithms.py
├── templates/
│   └── index.html
├── static/
│   ├── style.css
│   └── script.js
├── tests/
│   └── test_scheduler.py
└── docs/
    └── project_report.md
```

## 💻 System Requirements

- Python 3.10 or later
- A modern web browser (Chrome, Edge, Firefox, etc.)
- Internet connection for installing Python dependencies
- Windows, macOS, or Linux

## ⚙️ Installation and Setup

### Step 1: Clone the repository

Install Git if required, then run:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd SmartDisk_Final
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with the HTTPS URL of your GitHub repository.

Alternatively, download the repository as a ZIP file from GitHub and extract it.

### Step 2: Create a virtual environment

**Windows (Command Prompt):**

```bat
py -m venv .venv
.venv\Scripts\activate.bat
```

**Windows (PowerShell):**

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### Step 3: Install dependencies

Run the following command from the project root directory, where `requirements.txt` is located:

```bash
python -m pip install -r requirements.txt
```

If `python` is not recognized on Windows, use:

```bat
py -m pip install -r requirements.txt
```

## ▶️ Execution Instructions

After activating the virtual environment and installing dependencies, start the Flask application:

```bash
python app.py
```

On Windows, you can also use:

```bat
py app.py
```

When the server starts, open the following URL in your browser:

**http://127.0.0.1:5000**

Keep the terminal open while using the application.

To stop the server, press `Ctrl+C` in the terminal.

## 🧪 Testing Instructions

Run the automated test suite from the project root:

```bash
python -m unittest discover -s tests -v
```

On Windows, you can use:

```bat
py -m unittest discover -s tests -v
```

The tests are intended to check scheduling behavior, request handling, and calculation consistency. Ensure dependencies are installed before running the complete suite.

## 📊 Performance Metrics

SmartDisk can be used to examine metrics such as:

### 1. Total Head Movement

The total number of cylinder positions traversed by the disk head.

\[
M = \sum_{i=1}^{n}|H_i-H_{i-1}|
\]

### 2. Estimated Seek Time

The simulation estimates seek time from the total movement and the configured seek rate.

\[
T_{\text{seek}} = \frac{M}{R}
\]

Here, \(R\) is the configured movement rate.

### 3. Average Waiting Time

The average time requests wait before service begins.

\[
W_{\text{avg}} = \frac{\sum_{i=1}^{n}W_i}{n}
\]

### 4. Throughput

The number of completed requests per unit of elapsed simulation time.

\[
\text{Throughput} = \frac{\text{Completed Requests}}{\text{Elapsed Time}}
\]

The precise metric definitions depend on the simulation model implemented in the source code.

## 🔍 Algorithm Summary

| Algorithm | Working Principle | Limitation |
|---|---|---|
| FCFS | Services requests in arrival order | May cause excessive head movement |
| SSTF | Selects the nearest eligible request | Distant requests may experience long waits |
| SCAN | Sweeps across the disk and reverses direction | Requests near some regions may wait longer |
| C-SCAN | Services in one direction and wraps around | The return movement adds travel overhead |

No single algorithm is optimal for every workload. The simulator helps compare their behavior under the same request sequence.

## 🧠 Working Principle

1. The user configures disk parameters and request details.
2. The frontend sends the input to the Flask backend.
3. The scheduling engine processes requests using the selected algorithm.
4. The simulator calculates head movement and
