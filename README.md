<p align="center">
  <img src="assets/banner.png" alt="_CALCULATOR_ Banner" width="100%">
</p>

# ◈ Web Calculator

[![CI](https://github.com/ISBANDURAHUMAN-R/CODSOFT_taskno_CALCULATOR/actions/workflows/ci.yml/badge.svg)](https://github.com/ISBANDURAHUMAN-R/CODSOFT_taskno_CALCULATOR/actions/workflows/ci.yml)

## ◆ About the Project
Web Calculator is a responsive arithmetic calculator developed using HTML, CSS, and vanilla JavaScript. Created as part of the CodSoft Web Development Internship, it provides clean numerical computation across desktop and mobile screen sizes.

## ❖ Key Features
- Execution of core arithmetic operations (addition, subtraction, multiplication, division).
- Decimal input handling and mathematical expression evaluation.
- Clear screen (AC) and single-character delete functionality.
- Responsive CSS Grid keypad layout with active touch and click feedback.

## ◆ System Architecture
```mermaid
graph TD
    subgraph View ["Responsive CSS Grid UI"]
        Display[LCD Expression & Result Display]
        Keypad[CSS Grid Numeric & Operator Keypad]
    end

    subgraph Controller ["JavaScript Event Listener Engine"]
        Keypad --> ClickEvent[Click & Touch Event Handlers]
        ClickEvent --> ActionRouter{Token Type}
        ActionRouter -- Digit / Dot --> TokenAppend[Append Character to Expression]
        ActionRouter -- Operator --> OpAppend[Append Binary Operator]
        ActionRouter -- AC --> ClearAll[Reset Display Buffer]
        ActionRouter -- DEL --> DelChar[Pop Trailing Character]
        ActionRouter -- Equals --> EvalEngine[Expression Evaluation Engine]
    end

    subgraph Evaluation ["Evaluation & State Management"]
        TokenAppend --> Buffer[Current Expression String]
        OpAppend --> Buffer
        DelChar --> Buffer
        ClearAll --> Buffer
        Buffer --> Display
        EvalEngine --> SafeParse[Safe Math Parser & DivZero Guard]
        SafeParse --> OutputState[Format Floating Result]
        OutputState --> Display
    end
```

## ⬢ Technologies Used
- HTML5
- CSS3
- JavaScript (ES6)

## § Requirements
- Modern web browser

## ▲ Installation & Execution
```bash
# Open index.html directly or serve locally
python -m http.server 8000
```
Open `http://localhost:8000` in your web browser.

## ※ Developer
Developer: ISBANDU RAHUMAN R  
GitHub: https://github.com/ISBANDURAHUMAN-R
