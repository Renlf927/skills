# Evaluation Lessons From The Embedded Processors Revision Task

Use these lessons when the user asks for notes like the EPre / Embedded Processors revision project.

## What Failed

- The first version saved progress and covered many topics, but still leaned toward answer templates and did not always reconstruct the full PPT knowledge module.
- The second version improved formatting and became English-first, but the user still found it too much like direct answer aggregation.
- The user rejected a table where `Embedded system`, `MCU`, `MPU`, `RISC features`, `ARM Cortex series` and similar items were listed as separate short answers. The desired result was a focused module: for example, MCU and MPU definitions plus comparison across power, performance, integration, cost, size, peripherals, real-time suitability and scenario choice.

## What Worked Better

- Read all past papers again instead of trusting the prior output.
- Use extracted lecture text and cached JSON/text with page numbers.
- Organise notes by exam-tested knowledge modules:
  - Processor selection, ARM/RISC and memory map
  - GPIO/buttons/seven-segment
  - ADC/AnalogIn/quantisation
  - PWM/DAC/analogue output
  - Polling/interrupts/ISR
  - UART/SPI/I2C
  - Lifecycle/requirements/quality/firmware
  - RTOS scheduling
  - Testing/debugging
  - ARM assembly/DFG/code explanation
  - Modular programming
- Add `Related exam questions by knowledge point` tables inside the revision notes, not only in the separate mapping file.
- Use tables for definitions, comparisons, formulas, steps, API syntax and traps.

## Stable User Preferences

- The formal revision notes should be English-first because the exam is in English.
- Chinese can be used in conversation or brief hints only when useful.
- The user wants complete, clear knowledge modules, not normal PPT summaries and not short answer lists.
- If a lecture does not clearly contain a requested topic, mark it `Uncertain` instead of inventing a source.
- When outputs are iterative, preserve previous versions unless the user explicitly asks to overwrite.
- Always report the final file paths.
