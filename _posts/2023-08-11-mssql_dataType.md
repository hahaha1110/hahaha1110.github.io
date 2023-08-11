---
title: MSSQL 데이터 타입(자료형) 유형 정리
author: ha
date: 2023-08-11 15:00:00 +0900
categories: [SQL, MSSQL]
tags: [SQL, MSSQL]
render_with_liquid: false
img_path: /assets/img/20230811/
image: thumb1.png
---

<table class="se-table-content" style="">
                                    <tbody><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 19.19%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-ec748a89-c29e-44f6-9f16-846e95b78454"><span style="" class="se-fs- se-ff-   " id="SE-4c34871b-9472-4a3c-91ca-8fe0a03f5d92">유형</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-2f6fe952-aad4-4ceb-8589-323094efca5f"><span style="" class="se-fs- se-ff-   " id="SE-f98c0db4-05c0-43f6-9723-0938af978155">데이터 형식</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-b4265a1c-1228-4034-8535-f9a15a6f804a"><span style="" class="se-fs- se-ff-   " id="SE-c3d446b7-1857-4925-9db4-3cac8fe45dc5">설명</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="4" style="width: 19.19%; height: 172.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-9fed36f1-72bd-4638-bf0b-baf06419215c"><span style="" class="se-fs- se-ff-   " id="SE-a1caa6c9-2174-491c-8c44-ffb05cf088ce">정수</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-19132fde-c715-40c5-a299-0a44de0815b9"><span style="" class="se-fs- se-ff-   " id="SE-a06b296c-b5a8-4bb3-9b40-ec09ac15f533">BIGINT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-bebf29b0-1319-49b2-a084-c17a72c83655"><span style="" class="se-fs- se-ff-   " id="SE-7792b85c-d852-4fa2-90a8-8af56b7f116d">크기: 8 Byte</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-fa5ddd09-9dc6-446f-887b-4ac2833d8054"><span style="" class="se-fs- se-ff-   " id="SE-c3ca3c15-b4b1-44fb-b792-c9962cb2bb91">INT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-9b740090-6048-484c-a867-e8d3636dc2b6"><span style="" class="se-fs- se-ff-   " id="SE-86f879eb-475a-4b05-8bfe-6c5c1ef5fb22">크기: 4 Byte</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-036503f2-9b69-44d8-b894-c9f7154d1c85"><span style="" class="se-fs- se-ff-   " id="SE-721494b3-3021-40a7-9eb3-43dfefc99d4c">SMALLINT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-31b88daa-353c-4edd-81d8-b78b2492ecd6"><span style="" class="se-fs- se-ff-   " id="SE-e0b4daf5-cec9-4fd3-936e-ca56e1a4bf1d">크기: 2 Byte</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-18d10d32-51de-46ee-b7f9-9652096cc35e"><span style="" class="se-fs- se-ff-   " id="SE-b6feb00a-4351-4e5d-ba77-03f72b47210f">TINYINT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-61767b31-2f93-4c83-8f58-791d5a150103"><span style="" class="se-fs- se-ff-   " id="SE-1dea3118-4077-47cd-b9fb-af1feb6a88ee">크기: 1 Byte</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="5" style="width: 19.19%; height: 215.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-70763cb8-9b20-4a6e-96dd-6bfb2206902f"><span style="" class="se-fs- se-ff-   " id="SE-4b130e44-cb95-4536-8b72-91c312bf5de5">정확한 수치</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-6d1a7108-e35f-44a4-ac9c-a3583a563763"><span style="" class="se-fs- se-ff-   " id="SE-b078ccfa-bfcc-4e01-acea-ef4389181b8c">NUMERIC</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="2" style="width: 54.99%; height: 86.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-bfc57024-0945-4bbe-ba9f-02a2b10702fc"><span style="" class="se-fs- se-ff-   " id="SE-d1b63810-1f7b-4dfc-9082-33a84b5ff4a8">전체 자릿수와 소수 자릿수가 고정된 숫자 데이터 형식입니다. DECIMAL과 NUMERIC은 동의어이며 서로 대체해 사용할 수 있습니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-36831248-004a-4742-a311-ffe078023f0c"><span style="" class="se-fs- se-ff-   " id="SE-2ec503ca-0dfb-4515-a48b-72b0ac3ab8fa">DECIMAL</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-392d76e2-6b6c-46f2-8e10-7610bc1d9dd3"><span style="" class="se-fs- se-ff-   " id="SE-4cae4c2c-4dd2-483b-9875-50aaa018260c">BIT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-361d6595-7623-4034-abd3-eb7a3c315982"><span style="" class="se-fs- se-ff-   " id="SE-3610897e-556a-4c90-8569-156961209085">1, 0 또는 NULL 값을 가질 수 있는 정수 데이터 형식입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-140bbd39-f3f4-4e6b-8ebf-d348b8b3cfba"><span style="" class="se-fs- se-ff-   " id="SE-5faa48bb-3bdc-44f4-8ba4-cedf8c6a52c3">MONEY</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="2" style="width: 54.99%; height: 86.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-e31a16ea-5626-446c-97f6-547669aa56cf"><span style="" class="se-fs- se-ff-   " id="SE-d48659b2-2a0b-4aff-b58f-4edf93ed33b4">통화 또는 통화 값을 나타내는 데이터 형식입니다. MONEY 및 SMALLMONEY 데이터 형식은 나타내는 통화 단위의 1/10000까지 정확합니다. INFORMATICA의 경우 MONEY 및 SMALLMONEY 데이터 형식은 나타내는 통화 단위의 1/100까지 정확합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-d5a50e41-8479-47f9-8b6f-d955334c80d2"><span style="" class="se-fs- se-ff-   " id="SE-680760db-5e9d-4a0d-b377-b6b3a2a0dbf4">SMALLMONEY</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="2" style="width: 19.19%; height: 86.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-f22905dc-17e0-4785-a11f-f8b119128010"><span style="" class="se-fs- se-ff-   " id="SE-b160a7ce-056d-4f56-bd6d-2a7ce423e988">근사치</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-dc74d442-d8d2-433f-8df1-14ecc9c47d5c"><span style="" class="se-fs- se-ff-   " id="SE-27a8518f-c07a-4bd1-8645-c58d01825cc5">FLOAT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="2" style="width: 54.99%; height: 86.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-f3658e8b-6917-4f4d-a499-18ef50ab5cad"><span style="" class="se-fs- se-ff-   " id="SE-9a2d441a-4b5a-47d5-9f93-313c4ee4e34f">부동 소수점 숫자 데이터에 사용하는 근사 숫자 데이터 형식입니다. 부동 소수점 데이터는 근사값이므로 해당 데이터 형식 범위에 있는 모든 값을 정확하게 표현할 수는 없습니다. REAL의 ISO 동의어는 FLOAT(24) 입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-c18fd98e-bb42-4ada-aff0-fcaf17a7881e"><span style="" class="se-fs- se-ff-   " id="SE-586ac352-6d66-4ae7-92f8-f6b35f867bd4">REAL</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="6" style="width: 19.19%; height: 258.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-7f03d6fc-523f-4d9a-9f04-f627b76e6fdc"><span style="" class="se-fs- se-ff-   " id="SE-e129e251-2cd2-43fc-a8dd-198c9dfd5509">날짜 및 시간</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-93f4084e-d4c2-4651-9486-2090ecfaffad"><span style="" class="se-fs- se-ff-   " id="SE-fa500f89-32b1-4ae7-963d-aa5607f11926">DATE</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-76f64408-e550-42f8-8e85-af819d7d0c17"><span style="" class="se-fs- se-ff-   " id="SE-ea46c260-6399-4c38-b047-f6097ce75deb">SQL Server에서 날짜를 정의합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-e30808a1-e6fd-4fb2-b5cd-ccc655a78f42"><span style="" class="se-fs- se-ff-   " id="SE-295da2e1-a77c-4612-a079-7c56922ca57f">DATETIME2</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-9a8963c6-5398-43f5-b4ca-989b09e244f0"><span style="" class="se-fs- se-ff-   " id="SE-c572f9bc-1496-4313-9924-fa0b0655977f">24시간제 기준의 시간과 결합된 날짜를 정의합니다. DATETIME2는 더 큰 날짜 범위, 더 많은 기본 소수 자릿수, 선택 항목인 사용자 지정 전체 자릿수를 갖는 기존 DATETIME 형식의 확장으로 볼 수 있습니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-5a5a1b58-07e9-4160-a17a-3fec4550e8bc"><span style="" class="se-fs- se-ff-   " id="SE-96c02eaf-7ee2-4f77-8aa0-5b783515f2d6">DATETIME</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-33c2376d-89c0-46a0-a1a1-4eefaa658496"><span style="" class="se-fs- se-ff-   " id="SE-e651aace-1d86-4613-ac21-4035f9a17d19">소수 자릿수 초가 있는 24시간제 기준의 시간과 결합된 날짜를 정의합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-0da95f23-de8a-4a00-bb26-401d14c51f00"><span style="" class="se-fs- se-ff-   " id="SE-92d94397-ab31-430d-adcb-dd879f95343b">DATETIMEOFFSET</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-84af35a3-b25a-4fb3-8b7b-84637db67d39"><span style="" class="se-fs- se-ff-   " id="SE-5df29a7f-bb7e-49f1-a1ae-deeec6aa6048">표준 시간대를 인식하며 24시간제를 기준으로 하는 시간과 결합된 날짜를 정의합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-ecf06b72-c013-47f6-9ae6-839ba6dbf2da"><span style="" class="se-fs- se-ff-   " id="SE-6d114526-7cfa-48db-a3d1-3540a4894c2e">SMALLDATETIME</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-6a7135c6-8cb7-4f30-b3ab-4ea5317a767e"><span style="" class="se-fs- se-ff-   " id="SE-1bde704a-9707-4f50-941b-fbbc3d54ac42">날짜와 시간을 정의합니다. 시간은 하루 24시간을 기준으로 하며 초는 항상 소수 자릿수 없이 0(:00)으로 표시됩니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-f95f1257-36e7-4197-9cd3-7043a9459c25"><span style="" class="se-fs- se-ff-   " id="SE-e0da8bb6-c770-4858-b55d-973328315cf2">TIME</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-2d47ede8-604a-4fdb-95d7-d8e7ba1618f6"><span style="" class="se-fs- se-ff-   " id="SE-99f5ddec-bd09-418b-8e51-fe8d0d053448">시간을 정의합니다. 시간은 표준 시간대를 인식하지 않으며 24시간제를 기준으로 합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="3" style="width: 19.19%; height: 129.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-ab631a23-8eac-4001-928e-44c52d2ff7ab"><span style="" class="se-fs- se-ff-   " id="SE-5932d9f1-8fba-4583-b801-aeb767a30169">문자열</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-7e51841f-e4b9-4c9f-aa4b-593cb81309bd"><span style="" class="se-fs- se-ff-   " id="SE-195baa40-bd84-4472-9c8b-bd1ae7ce2308">CHAR</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-ec4b845e-1d58-4854-8dc5-75ed28810577"><span style="" class="se-fs- se-ff-   " id="SE-5e176d92-a444-401b-8671-433475e4f181">고정 크기 문자열 데이터 형식입니다. UTF-8 문자 인코딩을 사용합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-da0baaf4-0f29-41b1-b9cc-d1df8e5b05ba"><span style="" class="se-fs- se-ff-   " id="SE-8f6f3bb1-339e-40bc-abe2-f0f45a5e413d">VARCHAR</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-e32d3d26-095e-4728-b68a-2ee731cc60fa"><span style="" class="se-fs- se-ff-   " id="SE-ee34e3cc-8ca5-487c-8072-bba0b9824a39">가변 크기 문자열 데이터 형식입니다. UTF-8 문자 인코딩을 사용합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-6bb114dd-967f-4b54-9ec6-6798cda96806"><span style="" class="se-fs- se-ff-   " id="SE-e7fa5ff1-2464-46c5-8561-fd48a8ca4cac">TEXT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-273dcc06-0886-46b6-acfe-2a050e0cdd9e"><span style="" class="se-fs- se-ff-   " id="SE-26a2fce3-cffb-49de-ad78-666fa85ee6af">최대 문자열 길이가 2^31 - 1(2,147,483,647)인 비유니코드 가변 길이 데이터입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="3" style="width: 19.19%; height: 129.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-09b96b84-2cea-41b2-a4da-cae40b516495"><span style="" class="se-fs- se-ff-   " id="SE-fce28bcf-5ac1-4e2a-9048-312deba18b00">유니코드 문자열</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-7d5261f0-7c82-4752-b2fc-3b29f4187945"><span style="" class="se-fs- se-ff-   " id="SE-4552cb2a-0358-4f0d-aa64-8e3ff70e15da">NCHAR</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-f0161689-4f84-4438-974e-de907475e456"><span style="" class="se-fs- se-ff-   " id="SE-42ea21a0-19f0-4403-8627-5f970b3d1ccf">고정 크기 유니코드 문자열 데이터 형식입니다. UTF-16 문자 인코딩을 사용합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-c88ff1ce-dc8b-40f3-9d74-de759c6ff0d4"><span style="" class="se-fs- se-ff-   " id="SE-4e06a829-0d8e-47db-8eeb-2878470e504f">NVARCHAR</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-c2d2fa01-8a30-49ff-accd-566e9af40451"><span style="" class="se-fs- se-ff-   " id="SE-ed336a29-8f70-48eb-88cd-8c2c8c18c526">가변 크기 유니코드 문자열 데이터 형식입니다. UTF-16 문자 인코딩을 사용합니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-7ff18af4-dd1c-4c42-8a14-b6fcb9fd4481"><span style="" class="se-fs- se-ff-   " id="SE-2cd030f3-bc18-422c-9c31-4c6073c08c1f">NTEXT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-845a6f0b-ce2d-4b39-bb0d-67c53e6b4c4c"><span style="" class="se-fs- se-ff-   " id="SE-c48d8fec-06ef-4f74-bdcb-cc59326a1525">최대 문자열 길이가 2^30 - 1(1,073,741,823)바이트인 가변 길이 유니코드 데이터입니다. </span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="3" style="width: 19.19%; height: 129.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-f51ec7eb-3395-4afa-afb7-198e79801817"><span style="" class="se-fs- se-ff-   " id="SE-9f679abb-0112-4b98-b157-33562e2edd80">이진 문자열</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-fe1a53c1-ba33-405b-8fb2-2b1e75624283"><span style="" class="se-fs- se-ff-   " id="SE-7315782d-a503-4528-9f71-2d34eee6b6f8">BINARY</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-8e33d665-2a96-4fd1-a0b9-f0efe248689c"><span style="" class="se-fs- se-ff-   " id="SE-08a4f3f2-d74d-4d98-926d-d49372ab5111">고정 길이의 이진 데이터 형식입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-a805b050-0bc9-448d-aa21-7afed2b30859"><span style="" class="se-fs- se-ff-   " id="SE-76010698-36d2-42e5-9297-272377b14bbc">VARBINARY</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-7a189082-ca01-4a10-949a-b1f73eb1a654"><span style="" class="se-fs- se-ff-   " id="SE-54dd37ad-ef09-4641-976f-4348f0215943">가변 길이의 이진 데이터 형식입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-c6e28be4-7b69-4ffd-bd5a-df0b6ed1b10d"><span style="" class="se-fs- se-ff-   " id="SE-83fda16e-50e0-467f-9c0c-3c91a1caa3b6">IMAGE</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-265902d7-e9bc-4ffb-a9a1-d90b2157740f"><span style="" class="se-fs- se-ff-   " id="SE-74ff86aa-c816-41b8-8050-eab4635cf94f">0에서 2^31-1(2,147,483,647)바이트의 가변 길이 이진 데이터입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="6" style="width: 19.19%; height: 258.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-e47f9f02-20fe-4cd0-b2dd-acc40c4b6b53"><span style="" class="se-fs- se-ff-   " id="SE-fac3bb25-8a68-4191-b81b-4c10944868ce">기타 데이터 형식</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-0b7c0529-c206-4458-a1f8-e222a6b4caf3"><span style="" class="se-fs- se-ff-   " id="SE-7f230d12-10c1-491c-8dd7-59ed014c6b3a">CURSOR</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-f31165c4-4ef1-45f7-9186-f39e8ef5e952"><span style="" class="se-fs- se-ff-   " id="SE-9fb37a28-4eb0-422e-869c-6d1a4305ce1d">커서에 대한 참조가 들어 있는 변수 또는 저장 프로시저 OUTPUT 매개 변수의 데이터 형식입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-9d58aee4-6529-4e22-abd2-df2494de560e"><span style="" class="se-fs- se-ff-   " id="SE-8140d23d-5178-40d5-8ab3-2957b2ed53d9">ROWVERSION</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-a26d97da-8399-48ca-9ee0-5c3c21151898"><span style="" class="se-fs- se-ff-   " id="SE-e0cc227c-e1ea-40fb-b24c-befcc02f121b">데이터베이스 내에서 자동으로 생성된 고유 이진 숫자를 표시하는 데이터 형식입니다. </span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-84adec97-8f60-40e1-9295-756864e333bb"><span style="" class="se-fs- se-ff-   " id="SE-e0fedb26-d800-4fe7-bef7-ee3e500a8be6">HIERARCHYID</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-5e680256-17a8-4188-b97e-79843152dea7"><span style="" class="se-fs- se-ff-   " id="SE-e59117a9-f17e-4b6e-9f59-297a8688fe6a">HIERARCHYID 데이터 형식은 가변 길이의 시스템 데이터 형식입니다. HIERARCHYID는 계층에서의 위치를 나타내는 데 사용됩니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-bf93a9cc-736a-4ae0-bef7-3eef7f6f298e"><span style="" class="se-fs- se-ff-   " id="SE-0320770a-629d-475d-b29c-7bf7e003b860">UNIQUEIDENTIFIER</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-f28ad965-09b7-4abb-850d-44316f075a98"><span style="" class="se-fs- se-ff-   " id="SE-e08041bf-3ce2-4960-8aa2-1a5091241267">16바이트 GUID입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-2019787e-28b2-4f6f-bfea-0c4c4a8f59b0"><span style="" class="se-fs- se-ff-   " id="SE-cc1185ee-f1a6-4b6f-842e-9fea5e46c6b9">SQL_VARIANT</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-b8eb0a0a-78b2-4884-a97e-9c1fd1bdd627"><span style="" class="se-fs- se-ff-   " id="SE-598f035f-cb50-4ad0-b463-7858f9a60836">SQL Server에서 지원하는 여러 가지 데이터 형식의 값을 저장하는 데이터 형식입니다.</span></p></div>

                                    </td></tr><tr class="se-tr"><td class="se-cell" colspan="1" rowspan="1" style="width: 25.82%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align-center " style="" id="SE-f20e4354-8d21-4bfe-8940-d434bcfdf9d1"><span style="" class="se-fs- se-ff-   " id="SE-b04ef529-0bed-4c3f-b8f0-b58e5919b74d">XML</span></p></div>

                                    </td><td class="se-cell" colspan="1" rowspan="1" style="width: 54.99%; height: 43.0px;  ">

                                                <div class="se-module se-module-text"><p class="se-text-paragraph se-text-paragraph-align- " style="" id="SE-c3c158ff-0cf0-4cfc-8bc6-cafab9fac208"><span style="" class="se-fs- se-ff-   " id="SE-62dde0b9-bb02-4c75-8354-1ab852279c43">XML 데이터를 저장하는 데이터 형식입니다. xml 형식의 변수 또는 열에 xml 인스턴스를 저장할 수 있습니다.</span></p></div>

                                    </td></tr></tbody>
                                </table>

- 출처 :
- [https://m.blog.naver.com/PostView.naver?blogId=seek316&logNo=222108639805&categoryNo=67&proxyReferer=](https://m.blog.naver.com/PostView.naver?blogId=seek316&logNo=222108639805&categoryNo=67&proxyReferer=)

- [https://developerking.tistory.com/6](https://developerking.tistory.com/6)
