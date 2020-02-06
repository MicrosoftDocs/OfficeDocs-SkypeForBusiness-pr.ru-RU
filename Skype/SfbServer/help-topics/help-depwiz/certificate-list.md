---
title: Список сертификатов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Чтобы назначить сертификат, выберите сертификат в локальном хранилище сертификатов. Нажмите кнопку Далее, чтобы продолжить.
ms.openlocfilehash: ea7b17b3632fe91f67eeed214c866fbc1df57a3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823933"
---
# <a name="certificate-list"></a><span data-ttu-id="02f2e-104">Список сертификатов</span><span class="sxs-lookup"><span data-stu-id="02f2e-104">Certificate List</span></span>
 
<span data-ttu-id="02f2e-p102">Чтобы назначить сертификат, выберите сертификат в локальном хранилище сертификатов. Нажмите кнопку **Далее**, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="02f2e-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="02f2e-p103">На панели **Выбор сертификата из локального хранилища сертификатов** доступны для выбора действующие сертификаты, которые можно назначить для целевого типа использования. Чтобы проверить правильность выбора сертификата, нажмите кнопку **Просмотреть сведения о сертификате**. На вкладке **Сведения** можно посмотреть имя субъекта и альтернативные имена субъектов, настроенные для сертификата.</span><span class="sxs-lookup"><span data-stu-id="02f2e-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="02f2e-p104">На панели выбора может не оказаться ни одного сертификата. Причиной этого чаще всего является отсутствие доверенного корневого сертификата или сертификатов промежуточных центров сертификации, установленных на назначенном сервере, что не позволяет проверить сертификат и, следовательно, обеспечить цепочку доверия, создаваемую сертификатом для центра сертификации. Чтобы решить проблему, запросите и импортируйте цепочку сертификации, которая обычно содержит сертификат корневого центра сертификации, а также сертификаты всех промежуточных и выдающих центров сертификации.</span><span class="sxs-lookup"><span data-stu-id="02f2e-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

