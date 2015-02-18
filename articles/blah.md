**Low Storage Capacity: **

Trending per file share to understand the growth rate for next
corrective actions.

-   Alert based on VHD oversubscription when go over 200% warning and
    > 400% critical

-   Alert based on actual capacity on the file share beyond threshold.
    > (75% warning, 90% critical)

-   Trending on the capacity - short term and long term

-   Customer corrective action:

    -   Prevention: Do not provision to the file share that is already
        oversubscribed.

    -   Move VHD(s) to file share which is has capacity by using live
        storage migration or qsm.

    -   Purchase more storage disk thru long term trending analysis

**Monitoring:**

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
           Work Items                                                                                                                    Content                                                                                                                                              Owner                             Costing (dev/test)
  --- ---- ---------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------- --------------------
  1   P0   Understand each VHD capacity and VM/VHD (count) density per file share.                                                      Require Hyper-V team to provide method to understand the VHD oversubscription rate.                                                                   Hyper-V (Senthil and Patrick)      N/A exposed
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                              VMM (Keiko)                       

      P0   Understand VHD oversubscription rate                                                                                         Require Hyper-V team to provide method to understand the VHD oversubscription rate.                                                                   Hyper-V (Senthil and Patrick)      N/A exposed
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        VMM to capture the VHD oversubscription rate                                                                                                          VMM (Keiko)                       

      P0   Alert when VHD over subscription is beyond 200% for warning and 400% for critical.                                           OM should write a rule\\monitor and that rule\\monitor should create an alert                                                                         OM (Charlie and Daniel)           OM dev
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        To have both threshold configurable for users.                                                                                                                                          OM test

  2   P0   Understand per file share actual capacity and % full and alert when gone beyond threshold. (available thru VMM Storage MP)   Currently available. However, we may require to have threshold set for 75% warning and 90% critical. To have both threshold configurable for users.   OM (Charlie and Daniel)           OM dev 0.5days
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                OM test

  3   P1   Short term trending information on the immediate file share growth based on gathered file share used space.                  Short term:                                                                                                                                           ~~OM (Charlie and Daniel) or ~~   Advisor dev
                                                                                                                                                                                                                                                                                                                                
           Long term trending and analysis for capacity planning                                                                        Based on the OM alerting, customer to                                                                                                                 Advisor (Satya and Joe)           Advisor test
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        Require to understand what growth rate X means. Require to predict when the file share will be full.                                                                                    
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        Retention of the trending data to be Y days. OM monitoring rules will be needed to be created.                                                                                          
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        Long term:                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        Predict when new hardware needs to be purchased based on growth rate.                                                                                                                   
                                                                                                                                                                                                                                                                                                                                
                                                                                                                                        (e.g. - purchase new CPS hardware in 3-6month)                                                                                                                                          
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Remediation: **

      Items                                                                             Content                                                          Owner      Costing (dev/test)
  --- --------------------------------------------------------------------------------- ---------------------------------------------------------------- ---------- ----------------------------------
  1   If other file share disk space is available, run live storage migration or qsm.   Manually run live storage migration or qsm                       Customer   Test cost required (which team?)
  2   Purchase new CPS if entire capacity runs out.                                     Advisor to provide long term trending to predict next purchase   Customer   N/A

 

**Reference: **

-   Thin Provisioning :
    <http://itknowledgeexchange.techtarget.com/virtualization-pro/pointers-for-using-thin-provisioned-disks/>


