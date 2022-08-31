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
