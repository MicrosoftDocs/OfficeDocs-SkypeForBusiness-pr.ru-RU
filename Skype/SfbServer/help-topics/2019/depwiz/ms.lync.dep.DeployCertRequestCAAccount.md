---
title: Запрос сертификата (учетная запись центра сертификации)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: Для отправки запроса службе сертификации (ЦС) может потребоваться использовать учетные данные, отличные от тех, что зарегистрированы для пользователя, под которым вы вошли в систему.
ms.openlocfilehash: 8319b18340d705645529dba93ccfab40a96b68a2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705684"
---
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="02eae-103">Запрос сертификата (учетная запись центра сертификации)</span><span class="sxs-lookup"><span data-stu-id="02eae-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="02eae-104">Для отправки запроса службе сертификации (ЦС) может потребоваться использовать учетные данные, отличные от тех, что зарегистрированы для пользователя, под которым вы вошли в систему.</span><span class="sxs-lookup"><span data-stu-id="02eae-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="02eae-105">Чтобы разрешить запросу сертификата другого пользователя, установите этот флажок, **указав для центра сертификации альтернативные учетные данные**, а затем введите имя пользователя или имя пользователя _домена_\ _для пользователя_ , который может запросить сертификат.</span><span class="sxs-lookup"><span data-stu-id="02eae-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="02eae-106">В текстовом поле **Password (пароль** ) введите пароль для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="02eae-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="02eae-107">Затем имя пользователя и пароль отправляются в рамках процесса запроса сертификата, но не из фактического запроса сертификата в Интернет-центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="02eae-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  

