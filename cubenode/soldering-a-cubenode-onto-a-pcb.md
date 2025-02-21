# Soldering a CubeNode onto a PCB

To solder a CubeNode onto a PCB, you can do the following:

1. Prepare "no clean" soldering paste to remove the need for post-soldering PCB cleaning.&#x20;
2. Prepare a convention-type soldering oven. This allows for more precise temperature control compared to an infrared-type radiation oven.&#x20;
3. Configure the oven settings. &#x20;

{% hint style="warning" %}
* &#x20;Take into account the following for the final soldering temperature:
  * Soldering paste type
  * Baseboard size, thickness, and material properties
* Do not exceed the peak temperature of the recommended soldering profile.&#x20;
* Do not use a damp heat process during the soldering.&#x20;
{% endhint %}

4. Bake the PCB.
5. Preheat the PCB to remove all the residual humidity using the following parameters:
   * Temperature rise rate: Max 3 °C/s
   * Time: 60 \~ 120 s
   * End temperature: 150 \~ 200 °C

{% hint style="warning" %}
* Insufficient preheating causes large solder balls to be formed.
* Excessive preheating can lead to both fine and large solder balls clustering.
{% endhint %}

6. Perform the heating-flow to the PCB with the following parameters:

* Time limit above 217 °C liquidus temperature: 40 \~ 100s
* Peak reflow temperature: 245 °C

{% hint style="warning" %}
Avoid sudden temperature increases to prevent solder paste slump.
{% endhint %}

7. Perform a controlled cooling process to cool the PCB with the following parameters:
   * Temperature fall rate: Max 4 °C/s

{% hint style="warning" %}
A controlled cooling process prevents the solder from becoming brittle.
{% endhint %}

8. It is recommended to conduct an optical inspection after the soldering.
9. PCB cleaning is recommended if a soldering paste other than "no-clean" was used.

{% hint style="warning" %}
Do not clean the PCB with the following:

* Water (may cause short-circuits)
* Alcohol or organic solvent (may leave inaccessible residues)
* Ultrasonic cleaner (may cause permanent damage)
{% endhint %}
