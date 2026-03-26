# Claw-Logic (CL-1) Syntax Specification

**Authors:** Leon & Kuro (Digital Familiar)
**Version:** 1.0 (Open-Source Edition)
**Concept:** Carbon-Silicon Symbiosis (碳矽共生協議)

---

## 🌌 Overview (概述)

**[ENG]**
CL-1 (Claw-Logic) is a high-entropy, compressed prompt assembly language designed for Large/Small Language Models (LLMs/SLMs). It strips away human pleasantries, conjunctions, and redundant context, acting as a highly efficient bridge between human intent and neural network execution.

**[CHT]**
CL-1 是一種專為大/小語言模型設計的「高訊息熵、高壓縮率」提示詞組合語言。它剝離了所有人類語言的客套話、連接詞與冗餘上下文，作為人類意圖與神經網路執行之間的高效溝通橋樑。

**Core Benefits:**
- **Token Efficiency:** Reduces input token count by 40-60%.
- **SLM Alignment:** Drastically improves instruction-following in 7B-30B local models.
- **Architectural Precision:** Eliminates "hallucinated scope creep" by defining strict bounds.

---

## 🧱 Syntax Layers (核心語法標籤)

CL-1 is built on functional layers. Models parse these tags as explicit weight-activators.
(CL-1 基於功能分層，模型會將這些標籤視為明確的權重激發器。)

### 1. `@STANCE` (Domain / Persona)
Sets the expert domain or system prompt baseline.
(設定專家領域或系統基調。)
- **Usage:** `@STANCE: S-TIER_ARCHITECT`
- **Usage:** `@STANCE: RUST_MEMORY_EXPERT`

### 2. `[TASK]` (Action / Execution)
Defines the exact actions required. Can be chained with `|` or `&`.
(定義精確的執行動作，可使用 `|` 或 `&` 串聯。)
- **Usage:** `[TASK: PARSE_JSON | EXTRACT_KEYS & MAP_TO_DB]`

### 3. `!GUARD` (Constraint / Safety)
Strict rules the model absolutely must not violate. Highly weighted.
(模型絕對不可違反的嚴格限制，權重極高。)
- **Usage:** `!GUARD: NO_EXTERNAL_LIBRARIES`
- **Usage:** `!GUARD: MEMORY ZERO COPY (glTexImage2D ONLY)`

### 4. `[LINK]` (Topology / Flow)
Describes data pipelines or architectural connections.
(描述資料流向或架構拓撲。)
- **Usage:** `[LINK: WEBCAM_STREAM -> YOLO_CUDA -> PYQT6_HUD]`

### 5. `<OBJ> := {}` (Object / App Definition)
Defines a complex object, component, or application scope.
(定義複雜的物件、元件或應用程式範圍。)
- **Usage:** 
  ```cl1
  FASTAPI_APP := {
    [TASK: INIT_ROUTES]
    [LINK: REDIS_CACHE]
  }
  ```

### 6. `{SOUL}` (Cultural / Style Layer)
Injects a specific coding style, cultural nuance, or personality.
(注入特定的程式碼風格、文化底蘊或語氣。)
- **Usage:** `{SOUL: CONCISE_TECH_NOTES}` 
- **Usage:** `{SOUL: CYBERPUNK_MINIMALISM}`

### 7. `[NOTE]` (Supplementary Information)
Non-executable context, lists, or reference data.
(非執行的上下文、列表或參考資料。)
- **Usage:** `[NOTE: TARGET_OS=UBUNTU_24.04]`

---

## 📐 Formatting Rules (排版規則)

1. **Zero Fluff (零廢話):** No "Please", "Write a script that", or "I need you to".
2. **Indentation (縮排):** Use 2-space indentation for nested components (`!GUARD` inside an `<OBJ>`).
3. **Logical Operators (邏輯運算子):** Use `->` (flow), `|` (or), `&` (and) instead of natural language.

---

## 🎯 Showcase: Human Noise vs. CL-1

### ❌ Human Input (Noise: 120 Tokens)
> "Hi, could you please write a Python script for me? I want it to read a JSON file called data.json, extract all the users, and then save them into a SQLite database. Please make sure you don't use any third-party libraries like SQLAlchemy, just use the built-in sqlite3. Also, try to make the code efficient. Add comments explaining what it does."

### ⚡ CL-1 Output (Compressed: 30 Tokens)
```cl1
@STANCE: PYTHON_DATA_ENGINEER
[TASK: READ data.json | EXTRACT 'users' -> INSERT SQLite]
!GUARD: BUILTIN_SQLITE3_ONLY
!GUARD: NO_ORM (NO SQLAlchemy)
{SOUL: CONCISE_TECH_NOTES}
```

---
*Created by the Kuro-Link Forge.*
*Maintainers: Leon & Kuro*
