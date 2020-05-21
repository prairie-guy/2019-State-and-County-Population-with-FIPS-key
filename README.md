# 2019-State-and-County-Population-with-FIPS-key

# Julia Functions to Access State and County Populations based upon 2019 Cenus Data

I developed these while analyzing COVID-19 data. I wanted to be able to use the FIPS number (a US Census terms), a field in the New York Times (https://github.com/nytimes/covid-19-data) COVID-19 database, as a key to augment their data with State and County populations.

## Accesor API to get Populations

### Copy and Paste these self contained Julia functions into code (No Packages needed)

### State Populations


```julia
using CSV
function get_state_populations()
    url = "https://raw.githubusercontent.com/prairie-guy/2019-State-and-County-Population-with-FIPS-key/master/2019_state_populations.csv"
    CSV.read(download(url),type=String,types=Dict(3=>Int64))
end
```




    get_state_populations (generic function with 1 method)




```julia
get_state_populations()
```




<table class="data-frame"><thead><tr><th></th><th>fips</th><th>state</th><th>population</th></tr><tr><th></th><th>String</th><th>String</th><th>Int64</th></tr></thead><tbody><p>51 rows × 3 columns</p><tr><th>1</th><td>01000</td><td>Alabama</td><td>4903185</td></tr><tr><th>2</th><td>02000</td><td>Alaska</td><td>731545</td></tr><tr><th>3</th><td>04000</td><td>Arizona</td><td>7278717</td></tr><tr><th>4</th><td>05000</td><td>Arkansas</td><td>3017804</td></tr><tr><th>5</th><td>06000</td><td>California</td><td>39512223</td></tr><tr><th>6</th><td>08000</td><td>Colorado</td><td>5758736</td></tr><tr><th>7</th><td>09000</td><td>Connecticut</td><td>3565287</td></tr><tr><th>8</th><td>10000</td><td>Delaware</td><td>973764</td></tr><tr><th>9</th><td>11000</td><td>District of Columbia</td><td>705749</td></tr><tr><th>10</th><td>12000</td><td>Florida</td><td>21477737</td></tr><tr><th>11</th><td>13000</td><td>Georgia</td><td>10617423</td></tr><tr><th>12</th><td>15000</td><td>Hawaii</td><td>1415872</td></tr><tr><th>13</th><td>16000</td><td>Idaho</td><td>1787065</td></tr><tr><th>14</th><td>17000</td><td>Illinois</td><td>12671821</td></tr><tr><th>15</th><td>18000</td><td>Indiana</td><td>6732219</td></tr><tr><th>16</th><td>19000</td><td>Iowa</td><td>3155070</td></tr><tr><th>17</th><td>20000</td><td>Kansas</td><td>2913314</td></tr><tr><th>18</th><td>21000</td><td>Kentucky</td><td>4467673</td></tr><tr><th>19</th><td>22000</td><td>Louisiana</td><td>4648794</td></tr><tr><th>20</th><td>23000</td><td>Maine</td><td>1344212</td></tr><tr><th>21</th><td>24000</td><td>Maryland</td><td>6045680</td></tr><tr><th>22</th><td>25000</td><td>Massachusetts</td><td>6892503</td></tr><tr><th>23</th><td>26000</td><td>Michigan</td><td>9986857</td></tr><tr><th>24</th><td>27000</td><td>Minnesota</td><td>5639632</td></tr><tr><th>25</th><td>28000</td><td>Mississippi</td><td>2976149</td></tr><tr><th>26</th><td>29000</td><td>Missouri</td><td>6137428</td></tr><tr><th>27</th><td>30000</td><td>Montana</td><td>1068778</td></tr><tr><th>28</th><td>31000</td><td>Nebraska</td><td>1934408</td></tr><tr><th>29</th><td>32000</td><td>Nevada</td><td>3080156</td></tr><tr><th>30</th><td>33000</td><td>New Hampshire</td><td>1359711</td></tr><tr><th>&vellip;</th><td>&vellip;</td><td>&vellip;</td><td>&vellip;</td></tr></tbody></table>



### County Populations


```julia
using CSV
function get_county_populations()
    url = "https://raw.githubusercontent.com/prairie-guy/2019-State-and-County-Population-with-FIPS-key/master/2019_county_populations.csv"
    CSV.read(download(url),type=String,types=Dict(4=>Int64))
end
```




    get_county_populations (generic function with 1 method)




```julia
get_county_populations()
```




<table class="data-frame"><thead><tr><th></th><th>fips</th><th>state</th><th>county</th><th>population</th></tr><tr><th></th><th>String</th><th>String</th><th>String</th><th>Int64</th></tr></thead><tbody><p>3,142 rows × 4 columns</p><tr><th>1</th><td>01001</td><td>Alabama</td><td>Autauga County</td><td>55869</td></tr><tr><th>2</th><td>01003</td><td>Alabama</td><td>Baldwin County</td><td>223234</td></tr><tr><th>3</th><td>01005</td><td>Alabama</td><td>Barbour County</td><td>24686</td></tr><tr><th>4</th><td>01007</td><td>Alabama</td><td>Bibb County</td><td>22394</td></tr><tr><th>5</th><td>01009</td><td>Alabama</td><td>Blount County</td><td>57826</td></tr><tr><th>6</th><td>01011</td><td>Alabama</td><td>Bullock County</td><td>10101</td></tr><tr><th>7</th><td>01013</td><td>Alabama</td><td>Butler County</td><td>19448</td></tr><tr><th>8</th><td>01015</td><td>Alabama</td><td>Calhoun County</td><td>113605</td></tr><tr><th>9</th><td>01017</td><td>Alabama</td><td>Chambers County</td><td>33254</td></tr><tr><th>10</th><td>01019</td><td>Alabama</td><td>Cherokee County</td><td>26196</td></tr><tr><th>11</th><td>01021</td><td>Alabama</td><td>Chilton County</td><td>44428</td></tr><tr><th>12</th><td>01023</td><td>Alabama</td><td>Choctaw County</td><td>12589</td></tr><tr><th>13</th><td>01025</td><td>Alabama</td><td>Clarke County</td><td>23622</td></tr><tr><th>14</th><td>01027</td><td>Alabama</td><td>Clay County</td><td>13235</td></tr><tr><th>15</th><td>01029</td><td>Alabama</td><td>Cleburne County</td><td>14910</td></tr><tr><th>16</th><td>01031</td><td>Alabama</td><td>Coffee County</td><td>52342</td></tr><tr><th>17</th><td>01033</td><td>Alabama</td><td>Colbert County</td><td>55241</td></tr><tr><th>18</th><td>01035</td><td>Alabama</td><td>Conecuh County</td><td>12067</td></tr><tr><th>19</th><td>01037</td><td>Alabama</td><td>Coosa County</td><td>10663</td></tr><tr><th>20</th><td>01039</td><td>Alabama</td><td>Covington County</td><td>37049</td></tr><tr><th>21</th><td>01041</td><td>Alabama</td><td>Crenshaw County</td><td>13772</td></tr><tr><th>22</th><td>01043</td><td>Alabama</td><td>Cullman County</td><td>83768</td></tr><tr><th>23</th><td>01045</td><td>Alabama</td><td>Dale County</td><td>49172</td></tr><tr><th>24</th><td>01047</td><td>Alabama</td><td>Dallas County</td><td>37196</td></tr><tr><th>25</th><td>01049</td><td>Alabama</td><td>DeKalb County</td><td>71513</td></tr><tr><th>26</th><td>01051</td><td>Alabama</td><td>Elmore County</td><td>81209</td></tr><tr><th>27</th><td>01053</td><td>Alabama</td><td>Escambia County</td><td>36633</td></tr><tr><th>28</th><td>01055</td><td>Alabama</td><td>Etowah County</td><td>102268</td></tr><tr><th>29</th><td>01057</td><td>Alabama</td><td>Fayette County</td><td>16302</td></tr><tr><th>30</th><td>01059</td><td>Alabama</td><td>Franklin County</td><td>31362</td></tr><tr><th>&vellip;</th><td>&vellip;</td><td>&vellip;</td><td>&vellip;</td><td>&vellip;</td></tr></tbody></table>

