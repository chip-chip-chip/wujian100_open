read rtl code recording

1. IO
  input           PIN_EHS;                        //External high speed osc clock        
  input           PIN_ELS;                        //External low speed osc clock        
  output          POUT_EHS;                        //External high speed osc clock        
  output          POUT_ELS;                       //External high speed osc clock        
  inout           PAD_GPIO_0; ---  PAD_GPIO_31;   //GPIO signal          
  inout           PAD_JTAG_TCLK;                  //CPU JTAG TCLK      
  inout           PAD_JTAG_TMS;                     //CPU JTAG TMS      
  inout           PAD_MCURST;                       //PAD system reset，active low      
  inout           PAD_PWM_CH0; ---  PAD_PWM_CH9;   //PWM channel signal      
  inout           PAD_PWM_FAULT;      //different with userguide   (0-11)
  inout           PAD_USI0_NSS;  ---  PAD_USI1_NSS; --- PAD_USI2_NSS;       //USI0 Slave select  unified serial interface(USI)
  inout           PAD_USI0_SCLK; ---  PAD_USI1_SCLK; --- PAD_USI2_SCLK;        //USI0 Serial clock 
  inout           PAD_USI0_SD0;  ---  PAD_USI1_SD0;  --- PAD_USI2_SD0;       //USI0 Serial data0 
  inout           PAD_USI0_SD1;  ---  PAD_USI1_SD1;  --- PAD_USI2_SD1;       //USI0 Serial data1 
      
2. modules
  aou_top | pmu_dummy_top
          | gpio0_sec_top | gpio0 | gpio_top | gpio_apbif 
                                             | gpio_ctrl
          | rtc0_sec_top | rtc_pdu_top | rtc_cdr_sync | gated_clk_cell
                                       | rtc_clr_sync | gated_clk_cell
                                       | rtc_pdu_apbif| gated_clk_cell
                         | rtc_aou_top | rtc_cnt
                                       | rtc_ig
                                       | rtc_clk_div | gated_clk_cell
                                       | rtc_aou_apbf| gated_clk_cell        
  pdu_top | ahb_matrix_top | ahb_matrix_7_12_main
                           | ahbm_dummy_top （0,1,2）
                           | ahb_dummy_top (0,1,2,3, imemdummy,dmemdummy)
                           | dmac_top
          | ls_sub_top    | ahb_matrix_1_6_sub
                          | ahb_dummy_top (0,1,2,3)                         
          | apb0_sub_top  | csky_apb0_top
                          | tim0_sec_top
                          | tim2_sec_top
                          | tim4_sec_top
                          | tim6_sec_top
                          | usi0_sec_top
                          | usi2_sec_top
                          | apb_dummy_top (1,2,3,4,5, ,7,8,9)
                          | wdt_sec_top
                          | pwm_sec_top
          | apb1_sub_top  | csky_apb1_top
                          | tim1_sec_top
                          | tim3_sec_top
                          | tim5_sec_top
                          | tim7_sec_top
                          | usi1_sec_top
                          | apb_dummy_top (1,2,3,4,5,6,7,8,9)
  core_top | E902_20191018  | cr_bmu_top  | gated_clk_cell
                                          | cr_bmu_dbus_if
                                          | cr_bmu_ibus_if

                            | cr_clkrst_top | cr_clk_top
                                            | cr_rst_top
                            | cr_core_top | cr_core | cr_ifu_top | gated_clk_cell(cpuclk_cell_ifu,entry_ifu_misc_clkhdr)
                                                                 | cr_ifu_ibusif  | gated_clk_cell (addr_cnt_low,addr_cnt_high,sm_upd,)
                                                                 | cr_ifu_ibuf    | gated_clk_cell(push_upd,pop_upd)    
                                                                                  | cr_ifu_ibuf_entry ( 0,1,2,3,4,5) | gated_clk_cell 
                                                                 | cr_ifu_ifdp
                                                                 | cr_ifu_ifctrl
                                                                 | cr_ifu_randclk
                                                    | cr_iu_top  | gated_clk_cell (misc_gated_clk)
                                                                 | cr_iu_decd
                                                                 | cr_iu_oper | cr_iu_oper_gpr | cr_iu_gated_clk_reg (1, ,3,4,5,6,7,8,9,10,11,12,13,14,15) | gated_clk_cell
                                                                              | cr_iu_gated_clk_reg_timing | gated_clk_cell
                                                                              | gated_clk_cell
                                                                 | cr_iu_alu
                                                                 | cr_iu_mad | gated_clk_cell (mad_gated_clk,split_cnt_upd,sm_upd,)
                                                                 | cr_iu_branch
                                                                 | cr_iu_special
                                                                 | cr_iu_rbus
                                                                 | cr_iu_retire | gated_clk_cell(dbg_gated_clk,ext_int_gated_cell,)
                                                                 | cr_iu_wb | gated_clk_cell（wb_gated_clk，wb_data_buf_16_0_gated_clk,idx_buf_3_0_gated_clk）
                                                                 | cr_iu_pcgen | gated_clk_cell (curpc_gated_clk,curpc_30_11_gated_clk,)
                                                                 | cr_iu_vector | 
                                                                 | cr_iu_ctrl
                                                                 | cr_iu_randclk
                                                                 | cr_iu_hs_split
                                        
                                        
                                        
                                        
                                        
                                                    | cr_lsu_top | cr_lsu_ctrl
                                                                 | cr_lsu_dp | gated_clk_cell（x_size_buf_gated_clk，x_store_buffer_clk）
                                                                 | cr_lsu_randclk
                                                                 | cr_lsu_unalign                                   
                                                    | cr_cpo_top
                                          | cr_bmu_top
                                          | cr_sahbl_top | gated_clk_cell（gated_ahbl_cpuclk_cell）
                                                         | gated_ahbl_cpuclk_cell
                                                         | cr_ahbl_if
                                          | cr_iahbl_top | gated_clk_cell
                                                         | cr_ahbl_reg_arb
                                                         | cr_ahbl_if
                                          | cr_sys_io  | gated_clk_cell
                                          | cr_coretime_top | gated_clk_cell(reg,cnt,syn)
                                          | cr_cp0_top | gated_clk_cell（lpmd）
                                          | cr_cp0_iui
                                          | cr_cp0_lpmd | gated_clk_cell（lpmd）
                                          | cr_cp0_oreg
                                          | cr_cp0_status
                                          | cr_cp0_randclk
                            | cr_had_top
                            | cr_tcipif_top | cr_tcipif_behavior_bus | gated_clk_cell
                                            | cr_tcipif_dummy_bus | gated_clk_cell
                                            | cr_clic_top | gated_clk_cell(enable,pend,sample,pri,cfg_gated,output)
                                                          | cr_clic_reg_if
                                                          | cr_clic_arb
                                                          | cr_clic_kid
                                            | cr_pwrm_top_dummy
                                            | cr_coretim_top


A10a | gated_clk_cell
     | A186a0（A18549，A159）
     | A15（A18548，A15a，A18547）
     | A1867b（A15b，）
     | A45 （A18546）
     | A1862c （A15c）
     | A7f（A18545）
     | A1864d （A15d，）| A10a（A74，A1862d，A75）
     | A15e（A18544）



cr_iu_top
  retu_top
  PAD_OSC_IO (EHS ELS)
  PAD_DIG_IO
  PAD_DIG_IO (MCURST JTAG_TCLK JTAG_TMS GPIO_0 ~  GPIO_31  PWM_FAULT PWM_CH0 ~ CH11 USI0_SCLK USI0_SD0 USI0_SD1 USI0_NSS USI1,USI2)
  
  
  ![image text](https://github.com/chip-chip-chip/wujian100_open/blob/master/z_img/structure.png)
