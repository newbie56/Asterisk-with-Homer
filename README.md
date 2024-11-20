# Asterisk-with-Homer
## Running Asterisk with required modules
1. Run Asterisk using:
asterisk -cvvvvv

2. Load required modules:
module load res_hep.so
module load res_hep_pjsip.so 
module load res_hep_rtcp.so 
module load func_channel

3. Restart the Asterisk:
core reload

4. Access monitoring tools:
http://<serverip>:9080 - Homer
http://<serverip>:9030 - Grafana

