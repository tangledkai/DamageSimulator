# [TangledKai] Damage Simulator - V1.3.0

* Overview:
  * The Damage Simulator is a utility for TRPG and game design, built to model and test damage calculations. It supports basic arithmetic operations and incorporates three optional damage modifiers: Random     Bonus, Dice Roll Bonus, and Critical Hits. These modifiers can be toggled on or off to instantly simulate the outcome of various compounded effects.
* Formula at a Glance:
  * Final Result = A (operator) [ ( (B × Random%) + (B × Dice Roll%) ) × (Critical Multiplier, if crit) ]
* Core Calculation Logic:
  * The final calculation is based on two main operands, A (the initial value) and B (the base value for all modifications). The final result is calculated as: Final Result = A (operator) [ Modified_B ].
* Calculation Process:
  * Calculating the Base for the Second Operand (Modified_B):
  * Random Bonus Value = B * Random%
  * Dice Roll Bonus Value = B * (Sum of Dice Rolls / 100)
  * Pre-Crit Second Operand = Random Bonus Value + Dice Roll Bonus Value
  * Note: If a specific bonus is disabled, its value is treated as 0.
  * Note: If both "Random Bonus" and "Dice Roll Bonus" are disabled, the original base value B is used directly as the "Pre-Crit Second Operand".
* Applying Critical Hit:
  * The system checks for a critical hit. On a successful critical hit, the Pre-Crit Second Operand is multiplied by the Critical Damage Multiplier.
  * Modified_B = Pre-Crit Second Operand * Critical Damage%
  * If no critical hit occurs, the Modified_B is simply equal to the Pre-Crit Second Operand.
* Final Computation:
  * Final Result = A (+, -, ×, ÷) Modified_B
_____
# [TangledKai]_傷害模擬器-V1.3.0 

* 工具說明：
  * 傷害模擬器用於TRPG或遊戲設計時的工具，提供基礎的四則運算，預設隨機傷害、擲骰傷害、爆擊傷害等三種計算模式，可以隨時開啟或關閉，能快速計算當前的數值疊加效果 。
* 計算公式：
  *  A (四則運算符) [ ( (B * 隨機%) + (B * 擲骰%) ) * (爆擊倍率 IF 爆擊) ]
* 計算公式與流程：
  *  計算過程中的第一個數字為A，第二個數字為B
* 計算流程：
  *  計算基礎加成：
  *  隨機傷害值 = B * 隨機%
  *  擲骰傷害值 = B * (總擲骰點數 / 100)
  *  總加成值 = 隨機傷害值 + 擲骰傷害值
  *  註：如果某個開關關閉，該部分的值即為 0
  *  如果所有加成都關閉，則「總加成值」就是原始的 B
* 套用爆擊：
  *  系統進行爆擊判定，如果 爆擊成功，則 總加成值 = 總加成值 * 爆擊傷害%
  *  目前的邏輯是爆擊只會強化 B 這部分的傷害加成
* 執行最終運算：
  *  最終結果 = A (+, -, ×, ÷) 處理後的總加成值
* 當前公式總結：
  *  最終結果 = A (四則運算符) [ ( (B * 隨機%) + (B * 擲骰%) ) * (如果爆擊則乘上爆擊倍率) ]

![傷害計算器](https://github.com/user-attachments/assets/d53651cf-f5e9-43c5-9b51-0865a59778ff)








