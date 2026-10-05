# Learning-Sprint-2-Team-44
SE/CprE 4210: Learning Sprint #2 Team 44 
# Buffer Overflow Visualizer

## Project Description

This project is a small static educational website that demonstrates the basic idea of a **stack-based buffer overflow**. It is designed for students who are learning about memory safety and software security.

The visualization models a simple stack frame containing:

1. An 8-byte input buffer
2. A simulated saved frame pointer
3. A simulated return-address area
4. Other simulated stack data

When the user enters text, the application places one character into each simulated byte. If more than eight characters are entered, the additional characters are displayed in the neighboring memory areas.

### Important safety limitation

This is **not an exploit tool**. It does not access real process memory, generate shellcode, calculate real exploit offsets, or provide instructions for attacking a program. The memory layout is intentionally simplified for conceptual learning.

## Features

- Interactive text input
- "Fill Memory" button
- Reset button
- Byte-by-byte visualization
- Slider that allows the learner to reveal the input gradually
- Visual distinction between normal buffer contents and overwritten neighboring memory
- Explanation of the buffer, saved frame pointer, return address, and overflow
- Responsive layout that works on desktop and smaller screens
- Runs entirely in a standard web browser with no server or installation required

## Files

- `index.html` — the complete static website, including HTML, CSS, and JavaScript
- `README.md` — project description and usage information
- `reflection.md` — reflection on the development process and what was learned

## How to Run

No build system is required.

### Option 1: Deploy from GitHub
Under deployments click github-pages
Under github-pages click https://elisin-rgb.github.io/Learning-Sprint-2-Team-44/ to launch the website

### Option 2: Open locally

Download or clone the repository and double-click `index.html`.

### Option 3: Use a local web server

From the project directory, run:

```bash
python -m http.server
```

Then open the local address shown by Python, normally:

```text
http://localhost:8000
```

## How to Use the Visualization

1. Start with a short input such as `HELLO`.
2. Click **Fill Memory**.
3. Notice that the characters fit inside the 8-byte buffer.
4. Try a longer input such as `HELLOWORLD123`.
5. The status message reports that the input exceeds the buffer.
6. The additional characters appear in the simulated neighboring stack areas.
7. Move the **Show bytes** slider to reveal the input gradually.

## Learning Goal

The central concept is that a buffer has a finite amount of storage. If software writes more data than the buffer can hold without checking its bounds, data outside the intended buffer can be overwritten.

In a real program, the exact stack layout is architecture-, compiler-, and program-dependent. The simplified layout in this project is therefore a teaching model rather than a representation of every real stack frame.

## Development Approach

The application was created as a single-file static web application using:

- HTML for the page structure
- CSS for layout and visual feedback
- JavaScript for the interactive memory model

The JavaScript maintains a simple array of simulated stack regions and maps each character of the user's input to a byte position. The visualization is updated whenever the input or slider changes.

## AI-Assisted Development

AI assistance was used to help plan the educational interface, generate an initial implementation, explain the buffer-overflow concept, and refine the documentation. The resulting code was reviewed and tested manually to make sure the application stayed focused on education rather than real exploitation.


