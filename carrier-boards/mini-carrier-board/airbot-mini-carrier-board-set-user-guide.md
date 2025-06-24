# Airbot Systems Mini Carrier Board

The Airbot Systems Mini carrier board integrates all the wiring into a 50.5 x 57.5mm board to save both space and weight. It comes with a mini power distribution board (PDB) that can deliver up to 180A. The ultra-compact setup ensures easy and clean mounting on various types of chassis.​

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-x-prod.appspot.com_o_spaces_2F-LUhw7cdLeWVORgnTA3i_2Fuploads_2F2l1Ow7VWe8Sg7zFgyocs_2Fimage.avif" alt="" width="375"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-Mhq_IAzrCOz2ixfWsc3_2F-Mhqa9R_VlSMOI41uYCt_2FAirbot_20Mini_20Carrier_20Board.avif" alt=""><figcaption></figcaption></figure>

## Dimensions

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-MhvLADMbCAWmh9NBc1-_2F-MhvRJj39G7yC6NJr6Bb_2FAirbot_20MCB_20Dimension.avif" alt=""><figcaption></figcaption></figure>

## Features <a href="#features" id="features"></a>

* **Dual power inputs**: Provides redundancy; automatically switching to the second power source if the first one fails.
* **Power distribution and voltage protection**: Provides current to each connector.
* **Motor PWM signal distribution**: Supports up to eight motors.
* **RC input**: Features a standard 2.54mm servo PPM/S.BUS/Spectrum RC input, with +5v/+3.3v selectable power from the carrier board.
* **AUX VCC pins**: These pins are connected together, allowing the AUX rail to be powered externally.

## Interfaces <a href="#interfaces" id="interfaces"></a>

| Port                         | Connector on the Board      | Mating Connector |
| ---------------------------- | --------------------------- | ---------------- |
| I2C\_2 - CAN1 - CAN2         | JST GH: BM04B-GHS-TBT       | GHR-04V-S        |
| USB - TELEM1 - TELEM2 - GPS2 | JST GH: BM06B-GHS-TBT       | GHR-06V-S        |
| GPS1                         | JST GH: BM08B-GHS-TBT       | GHR-08V-S        |
| POWER1 - POWER2              | Molex CLIKMATE: 502443-0670 | 502439-0600      |

{% hint style="info" %}
The Airbot Systems carrier board connectors are the same as those on the standard carrier board
{% endhint %}

## Pinout <a href="#pinout" id="pinout"></a>

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-MhvLADMbCAWmh9NBc1-_2F-MhvgQ2EeQwpaQQPNC4M_2FAirbot_20MCB_20Detail_20Diagram.avif" alt=""><figcaption></figcaption></figure>

## RC Signal and Power Selection <a href="#rc-signal-and-power-selection" id="rc-signal-and-power-selection"></a>

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-MhvLADMbCAWmh9NBc1-_2F-MhvgfOo6YGBJCFvdE7Z_2FAirbot_20MCB_20Bottom (1).avif" alt=""><figcaption></figcaption></figure>

## Airbot Systems Power Distribution Board (optional) <a href="#airbot-systems-power-distribution-board-optional" id="airbot-systems-power-distribution-board-optional"></a>

The Airbot Systems PDB can be installed directly below the Airbot Systems Mini carrier board. It allows up to 180A through the ESC interface and provides four pairs of low-power pads (two on the top and two on the bottom). The mounting holes are aligned with those on the carrier board, allowing the boards to be stacked together, but separated by small nylon spacers.The PDB can not be in contact with any conductive materials. Ensure there is sufficient distance between the PDB and any conductive components to prevent short circuits.The following Github links can be used to revise and update the Airbot Systems Mini carrier board information:

{% hint style="danger" %}
The PDB can not be in contact with any conductive materials. Ensure there is sufficient distance between the PDB and any conductive components to prevent short circuits.
{% endhint %}

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-MhvLADMbCAWmh9NBc1-_2F-MhvgxJOvaPYp5chHIA5_2FAirbot_20MCB_20PDB.avif" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-legacy-files_o_assets_2F-LUhw7cdLeWVORgnTA3i_2F-MhvLADMbCAWmh9NBc1-_2F-Mhvh8YbJERxb2EO_PXl_2FAirbot_20MCB_20set_20with_20Cube_20Orange_20-_20Side.avif" alt=""><figcaption></figcaption></figure>

The following Github links can be used to revise and update the Airbot Systems Mini carrier board informatio&#x6E;**:**&#x20;

* [https://github.com/CubePilot/cubepilot-docs/tree/master/carrier-boards/airbot-mini-carrier-board](https://github.com/CubePilot/cubepilot-docs/tree/master/carrier-boards/airbot-mini-carrier-board)
* [https://github.com/CubePilot/cubepilot-docs/blob/master/carrier-boards/airbot-mini-carrier-board/airbot-mini-carrier-board-set-user-guide.md](../airbot-mini-carrier-board/airbot-mini-carrier-board-set-user-guide.md)
