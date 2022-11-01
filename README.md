# 2022_Robocon_circuit
**2022年ロボコンの回路**<br>
マスターブランチは保護されているので，各ブランチで必ずプルリクエストを送ってください．

回路図とピン配置をここに明記しておきます．<br>

- 上部機構
  - 回路図
    ![上部機構](https://user-images.githubusercontent.com/80198387/185569705-36741227-0238-4329-8269-7aa137394152.png)
    
    > **Warning**<br>
    > 回路図が一部変わっています．詳しくはIssaimaruまで...
  
  - ピン配置
  
    | ピン番号 | 機能 | 備考 |
    | :---: | :---: | :--: |
    | PB_8/D15 | I2C_SCL | MoterDriver-Controller v3との通信用(I2C)|
    | PB_9/D14 | I2C_SDA | 同様 |
    | PA_15 | UART_TX | 足回りのmbedとの通信用 |
    | PB_7 | UART_RX | 同様 |
    | PB_4/D5 | PWM1 | 上下機構のモータの制御用 |
    | PB_5/D4 | DIR1 | 同様 |
    | PB_10/D6 | PWM2 | 装填機構のモータの制御用 |
    | PB_3/D3 | DIR2 | 同様 |
    | PA_8/D7 | PWM3 | 射出機構のモータ制御用 |
    | PA_10/D2 | DIR3 | 同様 |
    | PA_1/A1 | LED1 | MDCとの通信確認用LED |
    | PA_4/A2 | LED2 | 足回りのmbedとの通信確認用LED |
    | PA_0/A0 | LED3 | 上下機構の速度確認用LED(PWMに対応) |
    | PB_0/A3 | LED4 | 上下機構の上昇確認用LED |
    | PC_1/A4 | LED5 | 上下機構の下降確認用LED |
    | PC_0/A6 | LED6 | 射出確認用LED |
    
- 足回り
  - 回路図
    ![足回り](https://user-images.githubusercontent.com/80198387/185569554-7d095d9b-2277-4369-bf48-2375935484d7.png)

    > **Warning**<br>
    > 回路図が一部変わっています．詳しくはIssaimaruまで...
    
  - ピン配置

    | ピン番号 | 機能 | 備考 |
    | :---: | :---: | :--: |
    | PB_8/D15 | I2C_SCL | MoterDriver-Controller v3との通信用(I2C)|
    | PB_9/D14 | I2C_SDA | 同様 |
    | PA_15 | TWE_TX | TWELITEとの通信用 |
    | PB_7 | TWE_RX | 同様 |
    | PA_12 | MCU_RX | 上部機構側mbedとの通信用 |
    | PA_11 | MCU_TX | 同様 |
    | PB_4/D5 | PWM1 | 三輪メカナムの正面側モータ制御用 |
    | PB_5/D4 | DIR1 | 同様 |
    | PB_10/D6 | PWM2 | 三輪メカナムの左側面側モータの制御用 |
    | PB_3/D3 | DIR2 | 同様 |
    | PA_8/D7 | PWM3 | 三輪メカナムの右側面側モータの制御用 |
    | PA_10/D2 | DIR3 | 同様 |
    | PA_0/A0 | LED1 | MDCとの通信確認用LED |
    | PA_1/A1 | LED2 | 上部機構側mbedとの通信確認用LED |
    | PA_4/A2 | LED3 | TWELITEとの通信確認用LED |
    
- 暴走対策機能付き非常停止スイッチ
  - 回路図
    ![暴走対策機能付き非常停止スイッチ](https://user-images.githubusercontent.com/80198387/187575599-e7619aea-3dc1-4c90-a574-2f65bee7aef9.png)

  - 接続方法<br>
    - INPUT1，INPUT2はPowerUnit BseriesのMILコネクタ部のうちのVCCとGNDに無理やりはんだ付けして配線を伸ばして2ピンのJST-XHで接続してください．
    - SW_INは非常停止スイッチと接続してください．
    - CTRLはPowerUnit BseriesのCTRLと接続してください．
    - SWITCHはPowerUnit BseriesのSWITCHと接続してください．
    
 - 上部機構用エンコーダー
  - 回路図
    ![上部機構用エンコーダー](https://user-images.githubusercontent.com/80198387/193417058-c3f58b3c-a31a-4396-a744-c2936ded76ef.png)

  - ピン配置
    | ピン番号 | 機能 | 備考 |
    | :---: | :---: | :--: |
    | PB_7/D4 | I2C_SDA | メインマイコンとの通信用 |
    | PB_6/D5 | I2C_SCL | 同様 |
    | PF_0/D7 | ENC1_A | ロリコン1のA相 |
    | PF_1/D8 | ENC1_B | ロリコン1のB相 |
    | PA_8/D9 | ENC1_X | ロリコン1のX相 |
    | PA_11/D10 | ENC2_A | ロリコン2のA相 |
    | PB_5/D11 | ENC2_B | ロリコン2のB相 |
    | PB_4/D12 | ENC2_X | ロリコン2のX相 |
    | PB_1/D6 | PHOTO_OUT | フォトインタラプタの入力(HI->物体有/LOW->物体無) |
    | PA_6/A5 | RED | テープLEDの赤色点灯用ピン |
    | PA_4/A3 | GREEN | テープLEDの緑色点灯用ピン |
    | PA_3/A2 | BLUE | テープLEDの青色点灯用ピン |
    
  - 足回り用ロリコン
    - 回路図<br>
      ![足回り用ロリコン](https://user-images.githubusercontent.com/80198387/194679919-a4d8bbbc-785c-45b8-91b9-a1de73a46089.png)<br>

    - ピン配置<br>
      | ピン番号 | 機能 | 備考 |
      | :---: | :---: | :--: |
      | PB_7/D4 | I2C_SDA | メインマイコンとの通信用 |
      | PB_6/D5 | I2C_SCL | 同様 |
      | PA_12/D2 | ENC1_A | ロリコン1のA相 |
      | PB_0/D3 | ENC1_B | ロリコン1のB相 |
      | PF_0/D7 | ENC2_A | ロリコン2のA相 |
      | PB_1/D6 | ENC2_B | ロリコン2のB相 |
      | PF_1/D8 | ENC3_A | ロリコン3のA相 |
      | PA_8/D9 | ENC3_B | ロリコン3のB相 |
      | PB_5/D11 | ENC4_A | ロリコン4のA相 |
      | PA_11/D10 | ENC4_B | ロリコン4のB相 |
      
  - 国技館射出
    - 回路図<br>
      ![国技館射出](https://user-images.githubusercontent.com/80198387/199213701-0def5a7b-3f51-46c5-b0ae-15a8d4d2cb61.png)<br>
      
    - ピン配置<br>
      | ピン番号 | 機能 | 備考 |
      | :---: | :---: | :--: |
      | PC_12 | UART_TX | 足回りとの通信用 |
      | PD_2 | UART_RX | 同様 |
      | PB_4 | PWM1 | モータ駆動用PWM出力ピン |
      | PB_5 | PWM2 | 同様 |
      | PB_3 | PWM3 | 同様 |
      | PA_10 | PWM4 | 同様 |
      | PA_2 | PWM5 | 同様 |
      | PA_3 | PWM6 | 同様 |
      | PB_10 | DIR1 | モータ回転方向信号出力ピン |
      | PA_8 | DIR2 | 同様 |
      | PA_9 | DIR3 | 同様 |
      | PC_7 | DIR4 | 同様 |
      | PB_6 | DIR5 | 同様 |
      | PA_7 | DIR6 | 同様 |
      | PD_5 | ENC1_B | ロリコン1のB相 |
      | PD_6 | ENC1_A | ロリコン1のA相 |
      | PD_7 | ENC2_B | ロリコン2のB相 |
      | PE_3 | ENC2_A | ロリコン2のA相 |
      | PF_1 | ENC3_B | ロリコン3のB相 |
      | PF_0 | ENC3_A | ロリコン3のA相 |
      | PD_1 | ENC4_B | ロリコン4のB相 |
      | PD_0 | ENC4_A | ロリコン4のA相 |
      | PG_0 | ENC5_B | ロリコン5のB相 |
      | PE_1 | ENC5_A | ロリコン5のA相 |
      | PG_9 | ENC6_B | ロリコン6のB相 |
      | PG_12 | ENC6_A | ロリコン6のA相 |
      | PD_14 | RED | テープLED 赤色 |
      | PD_15 | GREEN | テープLED 緑色 |
      | PE_9 | BLUE | テープLED 青色 |
      | PF_11 | LED1 | 確認用LED(任意) |
      | PE_0 | LED2 | 同様 |
      | PG_8 | LED3 | 同様 |
      | PG_5 | LED4 | 同様 |
      | PG_6 | LED5 | 同様 |

