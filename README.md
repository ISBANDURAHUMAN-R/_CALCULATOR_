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
        Display["LCD Expression &<br/>Result Display"]
        Keypad["CSS Grid Numeric &<br/>Operator Keypad"]
    end

    subgraph Controller ["JavaScript Event Listener Engine"]
        Keypad --> ClickEvent["Click & Touch<br/>Event Handlers"]
        ClickEvent --> ActionRouter{"Token Type"}
        ActionRouter -- Digit / Dot --> TokenAppend["Append Character<br/>to Expression"]
        ActionRouter -- Operator --> OpAppend["Append Binary<br/>Operator"]
        ActionRouter -- AC --> ClearAll["Reset Display<br/>Buffer"]
        ActionRouter -- DEL --> DelChar["Pop Trailing<br/>Character"]
        ActionRouter -- Equals --> EvalEngine["Expression Evaluation<br/>Engine"]
    end

    subgraph Evaluation ["Evaluation & State Management"]
        TokenAppend --> Buffer["Current Expression<br/>String"]
        OpAppend --> Buffer
        DelChar --> Buffer
        ClearAll --> Buffer
        Buffer --> Display
        EvalEngine --> SafeParse["Safe Math Parser &<br/>DivZero Guard"]
        SafeParse --> OutputState["Format Floating<br/>Result"]
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
