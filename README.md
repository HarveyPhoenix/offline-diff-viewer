# offline-diff-viewer

A diff viewer that gives you sharable diff view links but does not store your data. (This takes inspiration from typescript playground how it stores your code in url itself) but the for very large data we will be doing end to end encryption just like `excalidraw` so you can still have sharable links without worrying if you should store your enterprise data or not.

## :bangbang: No data sent to server
You can take a look at the source code itself. All your data is kept as hash fragment in URL which never makes its way to server. Totally avoiding man in middle and XSS attacks to steal your data or any data breach. The data always stays in your URL and browser and never makes its way on the wire. Thats the main motive behind developing this tool. More about reasoning, why and how can be found in [Motivation](#motivation) section below. 

# Formats currently supported

1. Any texual format (JSON, HTML, Plain text, JS, CSS and any text based file content)

# Upcoming support

1. Images
2. Audio wave format

## Reason for building yet another diff viewer tool

I realise we are missing a diff viewer that is

- Privacy focused
- Simple to use
- And most importantly does not store any data on server to give sharable diff urls

## Motivation

I realise as a developer community we are missing on a diff viewer tool that does not store your data on their server to give you links to diff view to share with your teams.
There can be serious implications of storing your enterprise data on some server that you don’t know anything about.

Also current diff tools lack one major ability that is to compare any two text blocks. Many diff viewers out there target specific text types like JSON etc which is not what we want most of the time.

Also due to lack of such tool, if you want to see the the diff again you have to do the following

1. Ask/get the data from someone/somewhere
2. Search for a diff viewer tool online
3. Copy paste the data sources to the tool
4. Compare and share findings

This is still a mechnical part that can be easily automated. But most such tools out there right now store your data to give you sharable diff URLs which was a concerning thing at least for me for security reasons.

The simplest solution in my opinion will be

1. Get the data just once
2. Search for diff tool online just once
3. Copy your data to the tool just once
4. Compare and get a sharable url that stores your data in link itself (Like typescript playground stores your code in link)

In the chase of one such tool I ended up creating one as I did not find any that satisfied my requirements.
This is open source and has very easy user interface. Here is the link to the tool https://diffviewer.vercel.app/
It has following benefits

1. Since the tool does not store your data on its server there is no server required in the tool
2. The tool is blazing fast
3. Most importantly the link can be shared with anyone without security concerns(Unless you share link itself over some insecure network)
4. As the link contains data whomever you share link with can get data too
5. Also note that the data is put with hash in url so server can not read the data

[Here is a link to sample diff view](https://diffviewer.vercel.app/v2/diff#H4sIAAAAAAAAA61dXZPUuJL9KwQv-3LHUZLr8z6pu2GAaXqGoIkh5u5sbMi2ylaXbRX-6KL6xv3vq5SrGWDIYy_FA_PBKaASSamTmSdT_35aFu3Tfz797z_rJ0_-Tf948uTPpzb78-k_n4h_PP7_1jZt97-1rgz9_J9PX1tX__n0E1zqL9B3hWvcIXcu--wzptK2HPCy-_SBmUr3ujZlVJvusw_nps5MM3z6V1f_lNhaN8fPPmD3_6uzrDFtO3xILBZRPIvW80jIzZ9P6WP_-cc3TJKsSdeNbTu33dIfyxl241yh628btasCKJQ3Ky9N1PTn2CPnm0hsIhkvIzkD9sTYHs3bclXo7GA4Y9IBlSrpHx62xmRR6irGoEv7-H_88qzjSJBJC7IHLdCcNehlX28bkznepMvS6DbTpfm2UUXyiMeqcg-2LHXkmpyx6mLUqJVfn1kkF_GISQvWpJu-afSRN-iZX8PUleW37amyEzxX-8bW3bax_iuXR7BUP_tf_sVfz99sEv4AiUiuIhGvgE1L1qbfdVkik8yTG1vb1H3bpvvMVAFeKLPXUe7uGUtehP_elr3N0L4T62gWiaWMNjGwZsVa80InieWteX_s_ElpGD-XH07wUu3bPjIZ5xImnCBvwnztF8Wvz2YNTFmzprwr9McOejdbtp3RjDFddYJXKvM_eaxc5y8BsNeGFfrQG-wZlt5rb6K5d9yrObBrw9r13pSJNcDR6caVtmacwiE9wWu117n_d279BjaRPe86ms-iVVgwuQRGiRlr1VvTJwbcsRe1_-MOuukK_W3DGv3XJzaqK0xlts5_ww5ctW9ceRz35Svvyxdz8hExWjHB04cbbVtIIBpbJUfG63UB1KrSR5eW5CzO3oTeGu8l5jLCq8WThxvdpMBN_GLqurFpwVh0d4ITZdMPwJhpW8-78NUiCqu0kcgcnjv8yzW6AI5Cpxdtqm3GGPRQ6VQPH0hVYZP-nBtJ0B0bb8gmKQSyh6cOF5kpgYe4LUxz5ByEbgc0U9suBRfSBB8uZ2tPFebRxpsyh0eHpww_W1NmLVyb3633ad82ZutX5p5go2yRn8npPP9ZLSOxHuMKgicLz_wVAhbmvU137bctyQ6EbZU3AZgxzaF5P72mu5WMQTRBAJ7Q6BTdQZ7mUdDDbbI8_fSBXDXm3jRJrUfu19GTI-fLiPg2cQa423jO8NrcIz99XRpbt1Vfdw9MpLf76xOF6lvduUwjgjqN1kkhKc7z15CMltA0njbc6qQB4dF7f1OWhrmD2sOA2sdgj3ZhsTvjLMVxtPTnaOljCYmctuQZwztXVeAOunJVwoV7XRrAO6Ur_RA2XdRz1kwLXxci2syIImyQy5Y8RbimswDiiDf0hx0MFxvt9o_4ThX7c-_UpbfGu24fF8WIe0ueIFyUFvmHF7pmN5vOA1iq0nuEyrTAmPGYdR5ojljMRpip5MnBC6trcHBudbP1X5Txc-2AVqrtm3vjg4h6Z5A_uBkhB0vvBDzXFqt1tEGOQPLk4NpvEsS0rwofFTTM4uzSAa1VYvPSJcaz6-huf9Z1tFhEfo2Ivy3RtSp5knDb6cbbBDbcS308sHFrWwyoU52tj3tIsMf528wfG7EMQfiIQTxP-MNfQ8icy1LvTMms0TEZ0L3KnP_ZutLNznRnHSPvDfzlKhaUpIPHiGcMF2SCsSAeDxm8fmt2jF_YPeIfVGbazNxHaX3WxltJymRFdBktkFGILxxA6sf_3XeNYShQmZ3gRpkkcAT-DpoW1Ul_ijytE_MohmvEc4SfLfJ0l7osdPVta7ZJAFvVGk_kDIgbpgV1dIDm8xAICRg6xDxBeG_rDNyoF54PVZZhCAc9oN0p-eP_AVdo3C3EfmmWnqB6gwRanpjnCG8NcAlXugH8oElPcK_SCqXmpm01Ch02xN3ikSA1BjkE1-ToHro21d57ZjYbvHvE7ymTZdq9aVr3k4_k69xE2wbaN0q4Kd8TU0bBGypRjBTzxOGt6-8tSmnl_qQw4V6jA3hQOv3Q28Z0hW3pV57lxSmEkLNF5P0ePlM8eaAqCm_R62OdOeZEpWUAPyqduP7M20iEhFz4F3LcMc8YnnlSh3zdW5ebhjMlawb0OKVaNMnfrXzYKmbhTIklPE88Z_AkqEaViNuCzXW3LWEPPhwySel4PjfNOSyjlfcMwm8zZAjPFK5sY8sS1L2ujc0LNn5IdydYzBT5gtL__ujcTMzbe4PoQppvIlT7inmu8EI3dscbdaO7Y2sZ7pNXAyqE6vemrs-rrYiFv1QXxE5H_ADPFC5dAosQL1yWuLL7tjVJPqBCKorwvj8cWqypliKpmLJEVeM5TxJe-y3SZijp80wfMi4c8iSOQBGrru86l9qu03wpZeLxkaFsTEZJ5N3mPFH4wxR99sXX-PoE6cZvoyNTSjnuTrCYTyykjIWtVGYVK0qRCIEyCnOeLrzRXWMfLOKnrm0dw0_3SQDFgjJY_pvpDOUVJqQa_fHxjG4ZR2t0guY8O3jp_wTvp4BDMKblbqCiCqBYqrYkun22d_MbTvi7Zx1toFiBJwY3xkdnLVidF96n2zqnIIEhdPlfnxAr1brcoULKpBCPtAp-34WMMArF5zxTuMgazxXAbfTSNY1N2IKrLh5xsVb7wnUu6VMcj09cs3hFNWS_bqSbgZ6CJw0vKbpBvs_1LScvyQIoNspzhpxKyuel6sTSe3Pv--J5tEYB0pxnDpcm3YGU8DNX66JnzEmyARVabd3H2hzOcxAxuTry5P5UreCZ4hnDM5vuwOK8a3qg_sm6EyySz7P2CRcYTUyZLEIRQlA2aAP3HM8drnWKMt3Py4rVnBnCRKpEX2ciysxZB2guhuXxxHuFLqUFUC24DIRD702S_HTpWNVZc_AfSAgX2SSqOuEQUdlYrkJea40CiQXPHt4VJtF9CejDM5d53sYqZ7ITLIyqvUP_fn7n_XZIm-CE1oInDX98mfP9W0Kr6Vxl-m-bcUxOsNgqv0xAOjfRXxNVFX7PzUhPAg3iWcMbksCRkg-4hUIzbHXfeUjkwV-fVwsnmeYi5LMELN8teMLw2vrvjTLclPNgDk6ZDKgo_h_5kYnSmA3VkOlaXaGIYsEThrcjodFtZQ7-VDAuoR1QYVXrKZ7WgHRPzArHC-J1lMlaIoe94EnCW5cWBu85k-mCSz12ARR3qm87z7yrqDtP5OiNCbLNGSWzkEWgGNFksFz0vE3ddmu_-Iv9nNOZR1zsVGbuPUHsvLM4NwtEvk7Eoe46Q1HFgqcM721Zma6DkXljbMsYdsgHVJSqO9gOl8ImSlKpFLYI9WQJb1meMNwQM4N1Cd22TAW2SgZUVGrQC4-k6yYeKjH35hAX8mbNkQdc8uTheWNQPsh2R9Ji3X_bLlM94qIOcujUdA7lhSau1tp7dgpuiT-gPbjk-cOtbQ0KKt57_8YJttpDAIVTaenZb6LrHfCAE24qT1Yl6VLXsY8CkT08iXhnqwo59EvD5FG6xGixV-3uuB-_mMZWhnKq_iitiNsh8rDkycP7BtVb3rsmY5Oqh8OAig8qO9ZZ3QI6NEUZSNaQsnukfLTk-cMf_Ug6NX1tuIacY6XT0qOiUW3h9j_tG5D0nhQYrUmBOgv9EXNoEM8brnUDtWeUE0-Z_PBuN6CiVd60xrPWzOqzAglPvRcLUm7CvMmSJw2_-N8K1StfeM7GBUZ3eQBFpw6e2yF3PZZ49PEdeQCi3VC4sOS5wjXlb4Ah3lGTKIbN1e2qTx8Qvdr64DdxbnfW4khBQgxJFbARZ8AzheeVQXrAF_7_2Tjc5AMq7lXR52aQmaB8ycQIiWg3yQLX_naFeeIlTxaeef4MVuu1qRntpndv9YM4qLTw59CZmpojzlol760H1aZEHmHFE4Tbom_oVEMhXbO1HVNnafMBFR_9tmtJ9LjX9TnqM0-7Z94hRLAuseKZwS_abwF_naM-vWeaehI5x5ANqDg-5rRGii2jfGdG7VKz0HgoYMJkhboh7i0IZd94mGEIfkE8Jh7UvC009nQTcj8nbSDdrDAqX_EU4ZVDVXFPxFOOIdgqgHJGJSPdlT4kOlNItxAhH0zkDTHRFZA6jjC3301mdmyWYXd_gqVQRx__ukPQmZy1Rp6GSgrzNvNojS7WFc8TfKxd9TVKazWm-Cp_9wUpPcFSqvo4prCd6LgFEbn1wFCRVTxd8F_aQPFZ31QkIGTihiR5xGUc8lvt3p0djw_5rRlptlbQLJ48PDP1EbgGT1FrmzHOwV9IAZVzVfn1snvY6jpBCy2jsFCSunLQ7briWcONzuu-4g36bbu1JbdIlRtQuVB6vy_R7TqtGrH2QSqJoYkNwdPE04WXfbVtLDhNz1OXfNucwnhILif0Vk8UnXnOLdehbARzj2ueMTxD_a6XVF9lNU3JgMqV2lLk3Zy7OKdtFq2iNWILa54tPM9Qe4duyiNnjEkHVK5VadvuJ09Vvec-1yJPuCnMo2sJKQLXPFF4YVyDkt433s0y5by8IkxuVGb88lhHtb3jeXdRUNyH62iJYog1zxYumsy2dyAtrI8l0_iuO8KkVn07UmudkuQRoYpHS4M72tY8V3jmGlSVfEc8nNOiZt2AykQddeEcSYXZfMIIyabsm2cHYraMFoj2rAFDcAfcS-QOpmFUGN0-gDJVe1NH1n337pIxmRFyIsgKnhFc24cHRN7eNK7PSnfPHJjd_hGXmfJb7OianUFebWRdfFgqFhGFCnhZeC7wukctUTfpq_LecBmRskptgKU5Na1peGimJa0o17uMVmOp-TXiA3WNFumivPdxDaf40QMqxwqs47HCasiMSkpcI0vAWAXdZMCQn03DiQAPW8JkrvYJSouOG0EqpTVtsQWyYcNf_1ee2NdQXPG-sO2O42fpYUBloVJdRTrl-x0mqkXWpDUnz7xCN8yG5wCv0kInDtCz10Rb0sbtv22SLR9xadU2QxNWRteHyiKbGTVCSUQ2N_z9P6K2emNSdtxSsQ-gvFPUNHt2US7oXjxtphYo2N-w4W__d7oujiBk-5c1JKFg7pmHAZU7v9ea3NFcH5N29v5c_Qt1fFKQPcP6lw3PBC4bm1tYQ73y1z1bwk_SAZWlqhOUhB8jAoHVDKJzlM3ZAO1iTzNRwBK91sfEcck2XQ6orNSHXtdd6n_tmQkq4mendDykBRueFlz4fYLKWG_Nl8rnzw1qCJO1J2k--ORLpaMMjTo8qXzlbxx0b24AF3CZu_9yKtTXnlp_1ab7ORs4BFC6QXrpfyc0OGFKYxCpFYkNUPIdOjc0b8lVukUNTyTPNDXbQ9glj7jcK5fVbkeV-9ruLD9cbloouho6a0i8CMODDSgr-L9xEI7-qruCDa3rAMoPk2O3abcrCZvj0NAloPxXzHjG8KvD9K3uXPuQPhyZumOtP31ANv5Y-a_8kV-saXfTLIy-mfmz9bhUf9b_8_QfTxt2bmMM2gZeVabMUPu-0dQfzbCHdkBnP2R-XmhmXS-iUGqAQxtB9vfFVzz0b31rQarFJRGaEyyU_2akmTs7J7IKWmBK9MB5BAJwvNvdEcZFut3rhuNFbfWIS7VvSNh4DgOP1yHFM5cR7NyfA0dBOZ4c2UPqf86x59WAxkr739UzvtqmZ9fxN9Fy41krHCXFb7g3pkM5xSYU5DrO9-2TTx-Yq2CQa3Rnz1Sfel8eyzCJScbIn0swYuHnvuxw29e9YXedjyQCulCd21OKMUofznJ61Ge8CV0q0QIO_QIN1b-6JjENkG2_JY7NBLF1E8ClOvj7dpCPnJ3P9oyCgnLvIiRuMwQauTJHzrvjfZ1pA7hSmQ_-EvfxBwgZveteDRwJhrMSMPIbAwfn3aS_Vbbl5uZV3gSPrj3rs_Vu2HZnGkW0aLEODYd4QM4cSH2u-vIeFR6ujbnnckDk7jy4UW3XZ9aFMUZnamO8A6cAg_LacKwHGF9040MFVI28KrS_a5gwo0oHVKs7XSZ9dfasZ6qqztdhvCYk53MwfuX6CIf-3Oj0RcP1DewqneYeTSYJTcd6djcRKdL9SYIlOwEyw5e6Bso_Ep65PeMVkrsBTdW-b8y9K_tz-o9JxrgYpjHJOZyUBbq8bjUWKbzwjplLb7V5ALO_OrzOHSIjaBQBuTkSLkGWOgfjFcIM2h5VutInV7rPWQVgWqXpgJvxtoFJp2gzD-NKBF1HMAiMQdj-aodntDmuWdLuCduq3D5UPvQ_j_-Q1CI0f45UIuWMP0PPK-LCiKe6mh2YZaoA5mrvSHLhA9pzpRabQT4bjwn_JBhKe2tKf-nDEUbPD7ZmLqKW-m7agtRLYbCZj2VPU3--u2Dk18gvEfYMMegkeqYrq4HTftWYUtfMGmV2QO2kRZpQnJBRSBaPZO5isOd-8xFniTr4LywbSDhN2J3K6_5M6XnIqpJsREAvgMre_uooUVr10mh2Do5OArhTnXaJRp5g4sMJ0YbibzFS-RIgp3DRZw3wBK9NnnMaOb9pCCyVbpGkedK6-EsnTKSl4T7fuTIvGuo9QfmeK703JWdNng5opR5slVi0OFOzI8slPdIBx2gK0GB86Vk-kpb6YLrj7tBkP6D1lDGnE-Rj3pUtJDk12OEggdjqrfN_hE0Bebv035hbnSYJoFN3zlU_QG9FTYTzTbSgFBacuQQaCS9dbbdwFPJzm7GCuMQEcK-SvqX5Ce3BGHSMpuWFKY9AqUZPs-EgBQko9pXu0FiIY_WVLP1z6pYN6AeVFjbVuesam_RQSz9lZtFsfcqOjE3IAhfQz42uISn1XDv7aoN-MU08zU8faEbmiY8FDlIOnQ5UqoQzQmc837kqaOQKDB10s3VcmJrmA9qqwh1osOb24JodIglj3fpDPTn8gP2rAgwfeK395VqjA3Vp6u6BrYwlA9r5iOi8NIJ3d-S-F9Ec0YQ5uFZf6qZC9O1W1_mBc3ZFO6C9Mh91hcWyE1pRZiHwIcGPgDEdMOfa1jXwCd4TFq6qODVWcoJ_bMdQMIiO0UiqBzw84rfTHWwY8ofC1jkTNSTlCT4onaSU6Yn0WbXKxZouJNLOwpkXAiUUOtMWsOhfJZlhCyrlCf6oSqzGmFZ7DWOlwrQYCu_g-ylgzoquQdb02rPxih2yshvQozqYpPYE5NyXvUi7EGZoLmGgCvKlv6O6ww2NsmYScfdVAB_U0flfZeHgrwm2-CVZUYPnSD47BozunTU0zhPwbccVV7vUQ2KmMpOZtDov6bsJN6kIsR1y1wJQuReUswJKs-va5gVzl-a7AAqhctsVfcILZ8eSBnKYPbLB0zPnYBLbRWVL4KbDbHC2kVgnj7iQ6mDb9PsTvcPQvziihVnBtDVoC3pBKnE0w-fZf13UXe9qbgB_pgdYxMrUuc7yHzB5bb2mafUregcGLxLP3S6PnopCqYzmnk9KEsLEXO11lxZn9ziFJyTjYfwsns0IUm-_6Nrcgyvnt7ToTFO6mnFsd-7TB8RC2bozKPE2KVwIoTc1D2J-DWT0V2P0-p1jI7u0I0ws_SId9_pcYzzF8aszo8w1nHcMjKFp2xq_KaCbmgbGcfO2k0dcrPwKtZ3OG43eIpp2lsK-W9NLI3AGfwzmvF8FAQi6gtyuZacFpwMq1urenxXXILnFtIwcSRNmNIpfxjgjBybe6KbzBBk4iNdUHSk5EleVJ5imM9qkNDRN_ABfIpqgEpxHcZiLNdJtF4MJje912RWoVvxed5Xrc8b3HQ4nWGhVGdP16KmbKYosak-ZUWV1AaM8QOZuSVAF4iJ6Pqa2teu4N2La_K9PiMSHe2E825kzuMXycUARsTtYJAJlPO80UBro1pAP4BpwqvYEi1Rt_c-PPm46Oq8xTHomceAcVSAkmLHyqrWZA7vvRu85PYmtCBOZquDTphO1JOQfNhGlVKEtaOP9Vpp6h4op_qSxfRFOD6gwqk0tJVyoXpSe3zJNod58eBkCvm86B9HezbHp4PNRV56pc7suJYxGNk5ze1Or4uuhV2Iz9sIpeEjqeaXrHj7M-JKmGRrmAjbFgIqcItnqvFkR5Bt84LehwAk_6APyj56YG1jPuyGxKjtFJq1OsCjUod86lLAbrU_607Qgefd6ZBYykgRSTzHSr9_W7pCxioV2QIVVhxjUJka7PmbhuTIfBeJHJkGb8VvXwifLnmf02hWT0WrMgIo7ldKbdGUJvN00QjSj1E-IMuZQpw443rO-TC1irzc6ZycwZVUAxe5HzdQMHm42DxEG9HIx6Jegt0DR2Jjbjqp3THyRtQMqypH7aHxS9WIRukAXY52tAryicOWSBFhyoDYB9twMqKhG-icnRX2LQY5OOWE44kKiybQ6hQ8tFX1D87yY9q8yfcRFrbLKPZxdp6QiZXinbB1jcXAMZkm9Km0LjHqvbcdrSezhBAunqqOPttJzu_RCH5jYEEf9zi332tgSTgWl6N0w-boyGVCxV9qh6HxiEDtbhn23wp27c-DgvM_Gc7EuTeW_dJYzvKdJHnHxQbVFT85hCwfGjHoG0gXPSKwJo1iQ5Lq4NyV02temsIyD0zvCRKP87wkih2kyjNAu4GO9BZRhgFLrtUW07XeXGzYTtLsfUNGO3z6TXs5dh5CVUsQSDpYTIBt07UzdaPSU10vdtuwY_iKAolMpiuqmvXxFs2b9D_LZME_HJ0uGoA60UtJNytE22wZQ9KqvUbJ70rNKsyAoCb2hcNisABnvd0MXJWLVOn1-b0vu-c-u8u454OLekwPUGTrGRamiH1Koiwhm8AXoePhliFogr-50jXzbXfvpA-Kgij4Zm8M2jZaKaE7hD92t37nzLmrboSGat4UGz2Dp9gSLj6GPN4fjSSbMlgsjDOldbTitbA7G_71B0dwzw3Xu7jMPieMPGQ0cuPU66OrhEEMBJlD_7vd13dk71Cbu79u6KzTrt--bvz4hHv6S0J0tWCDiI8Ye0o1nvHVvvvJmXycc_b2py4zJNu7zEyxnU2bRTuz0mocpH5JWDfIfULUszc7fKRlIzr3U9G4Sd5iKAZXiM7Ujm0SdsA_XsxAW0dvA39tzc6tLC2bl3dLIKE6N3gZQShXuJ3DLTmDbQYKxidaUCoYVPtDWeqW74ognL1y5vunYNxPS9ATLWN1ZPdJ8PKkqFtE0zdnI6zAx8BMvTelgWPSW5IvftqdoCJNz1epygmMYDfIoQ0KqdBIMw0UCr3n5mAelTd-6Q9JzU4ySZkDlQhVpvJydnV4MISsps9DiCDC8NTTR4TEsVaW_-iaf09T0EZdLlTba5m3omfzu3Bw9I7cJRTC4QihqfecaVKnU1b5lK7BdeoLlSplyr-EBGhNnSEnyxkC9oc9GDcfhwXZIVS_qynETDXc6gHKtjG66glpaQWg06UlGKqksR17ugd25tm1RKa_hRoFWuYfkRvlf36NHC6cNMKIyFwmEY9hoAx56uGxg39B703Z7T2wYR3A4wVI_qpnO89NxPOgwlqNMG-XkUB7hF9Ow_TblXQBlMqqXmcbg6NQsQhc4FP9IQOBe6qNBid-jP-bsy5_tgNKARpgunabOnIUZMnEYawqLxGioO1qaMMaIcdB3YYxRIzNFg5m22x8w1ow6i2mOkRh5h2MO3lh7qf21gSRnZr933FyzIhtQSX2rcN7cWPA9dHAEDw2fuRIz0KnWFkib8LMtHfO-kN4SJreqPqLywpShX9RMPLzCM3L-way5K9fATOKVDuMeLKcDTNNPH5C5ovxKeA0zrb_3ulnTuyIkP4fT8-YzPjp4XlWomfjW9Q_MYHDTEiaLUbHphGdKZXiqXc5nEXylNJ7xvvmWRv-jxfndNDVjSntPmLR-SajJodJUOTHIr00QA8fhOQcSA8NwJwZPjtEIXdQAZVviywxPywZU3v3Ah1eXwyhNEUaZwR3He-qLEj9jVZYHxz2ZpJMTLHefZhyf0-1JFIdmfC0ieIAE6vf-mvv_rexIAgXm7mnbAZWlOhQusjVHPCfeo8Ta4jAfdAP3HJps2Cd4edJCVwk7uZlW6PETspr2LOGUlZoJiniCqnEBE3KoyUbjN5QuMq7WkGgPyVqRFd_tq8PsFGrDhUl5ELY9rywclvD8I1vfNoYw6VSt23EN3GjP6mx4e5l-wCgHuIFfzVfvaHydJugzvy2Yc1M3Ayr39PR8W2QOBdQT6AFlrWneCD2YjYWKc94kf_1DbUjXWd0xk-jT6gTLD94km5nwFA8IRUf7HlahYiJirOCJgT23utE_wQYBEtJyW649BFA2KklS2PU97e6ZbcKFul5EnwbRDiMZy6J9TW7n6T-f_kZDc2tdPnnn9_swrfERuirobetsQP7zf73yDBOBowAA)

## TODO/Upcoming features

Please check all To dos and upcoming things [here](https://github.com/technikhil314/offline-diff-viewer/projects/1)

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

## Self Host
This guide provides detailed instructions on how to self-host the offline-diff-viewer application using Docker and Docker Compose. Self-hosting allows you to run the application on your own server, providing you with full control over its environment and configuration.

### Building and Running the Docker Container
1. Build the Docker Image
```bash
$ docker build -t offline-diff-viewer .
```
2. Run the Docker Container via docker run command
```bash
$ docker run -d \
  --name offline-diff-viewer \
  -p 3000:80 \
  --security-opt no-new-privileges:true \
  -v /var/log/nginx:/var/log/nginx \
  --restart unless-stopped \
  -e NODE_ENV=production \
  -e NODE_OPTIONS=--openssl-legacy-provider \
  offline-diff-viewer
```

### Running the Container with Docker Compose
```bash
$ docker compose up -d --build
```
