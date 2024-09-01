# UART Interface

## Parameters
| Parameters           | Values                                 | Description                        |
|----------------------|----------------------------------------|------------------------------------|
| Baud Rate            | no limit                               | Bits per second                    |
| Number of Data Bits  | `5`, `6`, `7`, `8`                     | Number of data bits in each packet |
| Parity               | `none`, `odd`, `even` | **`none`:** no parity bit<br>**`odd`:** set to 1 if the number of 1s in data is even to make number of 1s in data+parity odd. Otherwise is set to zero<br>**`even`:** set to 1 if the number of 1s in data is odd to make number of 1s in data+parity even. Otherwise is set to zero |
| 2nd Stop bits        | `0`, `1`                               | Use an additional stop bit if set to 1 |



## Functions
<table>

<tr>
<th> Definition </th>
<th> Description </th>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
bit set_baud_rate(int baud_rate);
```
</td>
<td>
Sets the baud rate for the UART interface. <br>
Returns 1 is successful, otherwise 0 if TX or RX is busy.
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
int get_baud_rate();
```
</td>
<td>
Returns the current Baud rate.
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
bit set_num_data(int num_data);
```
</td>
<td>
Sets the number of data bits in each packets. Return success as 1, if num_data is within 5-8 and the TX and RX is not busy. Otherwise return fail as 0.
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
int get_num_data();
```
</td>
<td>
Returns the current number of data bits in each packet.
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
bit set_parity(int parity);
```
</td>
<td>
Sets the parity for the UART interface. Parity can be set to only 0-4 and only then will return success as 1 is the TX and RX is not busy. Otherwise return fail as 0.<br><b>parity value interpretations: </b><b>0</b><i>:none</i> </b><b>1</b><i>:odd</i> </b><b>2</b><i>:even</i> 
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
int get_parity();
```
</td>
<td>
Returns the current parity.<br><b>parity value interpretations: </b><b>0</b><i>:none</i> </b><b>1</b><i>:odd</i> </b><b>2</b><i>:even</i> 
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
bit set_stop2(bit en);
```
</td>
<td>
Enable or disable second additional stop bit. Returns success as 1 if TX and RX is not busy. Otherwise return fail as 0. 
</td>
</tr>

<!---------------------------------------------------------------------------------------->
<tr>
<td>

```SV
bit get_stop2();
```
</td>
<td>
Returns the whether to use additional stop bit.
</td>
</tr>


</table>


