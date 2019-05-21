---
title: Мастер сертификатов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: 'В мастере сертификатов выполняются следующие операции с сертификатами: Запрос, Назначить, Удалить и Просмотреть. Необходимо войти в систему с правами участника группы RTCUniversalServerAdmins. Для запроса сертификата из общедоступного центра сертификации не требуется участие в других группах. Чтобы запросить сертификат из инфраструктуры открытых ключей Организации (PKI), вам нужно подтвердить дополнительные возможности, которые вам понадобятся. В ходе задачи запроса вы можете ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата от ЦС, выдающего PKI.'
ms.openlocfilehash: daafbdd6730b86b7509323528405bec5277d264d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298963"
---
# <a name="certificate-wizard"></a><span data-ttu-id="b772a-107">Мастер сертификатов</span><span class="sxs-lookup"><span data-stu-id="b772a-107">Certificate Wizard</span></span>
 
<span data-ttu-id="b772a-108">В мастере сертификатов выполняются следующие операции с сертификатами: **Запрос**, **Назначить**, **Удалить** и **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="b772a-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="b772a-109">Необходимо войти в систему с правами участника группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b772a-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="b772a-110">Для запроса сертификата из общедоступного центра сертификации не требуется участие в других группах.</span><span class="sxs-lookup"><span data-stu-id="b772a-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="b772a-111">Чтобы запросить сертификат из инфраструктуры открытых ключей Организации (PKI), вам нужно подтвердить дополнительные возможности, которые вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="b772a-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="b772a-112">В ходе задачи запроса вы можете ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата от ЦС, выдающего PKI.</span><span class="sxs-lookup"><span data-stu-id="b772a-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="b772a-113">Для запроса нового сертификата нажмите кнопку **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="b772a-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="b772a-114">Для назначения сертификата, который еще не назначен, нажмите кнопку **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="b772a-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="b772a-115">Для удаления назначенного сертификата нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b772a-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b772a-p103">Кнопка **Удалить** доступна только при наличии назначенного сертификата. Если кнопка **Удалить** отображается серым цветом и недоступна, ни один сертификат не назначен.</span><span class="sxs-lookup"><span data-stu-id="b772a-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="b772a-118">Для просмотра назначенного сертификата нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="b772a-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b772a-p104">Кнопка **Просмотреть** доступна только при наличии назначенного сертификата. Если кнопка **Просмотреть** отображается серым цветом и недоступна, ни один сертификат не назначен.</span><span class="sxs-lookup"><span data-stu-id="b772a-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="b772a-121">Для обновления текущего экрана назначения сертификатов нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="b772a-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="b772a-122">Для импорта сертификата, отсутствующего в хранилище сертификатов, нажмите кнопку **Импорт сертификата**.</span><span class="sxs-lookup"><span data-stu-id="b772a-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b772a-123">Функция **Импорт сертификата** обычно применяется при необходимости в обработке сертификата, полученного без формирования запроса в мастере сертификатов.</span><span class="sxs-lookup"><span data-stu-id="b772a-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="b772a-124">Например, доступ к сертификату может быть предоставлен создавшим его администратором инфраструктуры открытых ключей.</span><span class="sxs-lookup"><span data-stu-id="b772a-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="b772a-125">Используйте **Импорт сертификата** для импорта сертификата в хранилище сертификатов компьютера и для предоставления доступа к нему в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b772a-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="b772a-p106">Если запрос сертификата из центра сертификации в организации требует утверждения администратором центра сертификации, для завершения процедуры запроса выберите **Обработать отложенный запрос**. Запрос сертификата возвращает состояние "отложен"; отображается также идентификационный номер отложенного запроса. Для продолжения обработки отложенного сертификата нажмите кнопку **Обновить**; при этом становится доступной кнопка **Обработать отложенный запрос**. Кнопка **Обработать отложенный запрос** больше не отображается серым цветом. Это делает возможной попытку извлечения отложенного запроса, но состояние "отложен" сохраняется до выпуска сертификата или отказа в его выпуске администратором центра сертификации. При отсутствии допустимых отложенных запросов, созданных с помощью мастера сертификатов, эта кнопка не доступна.</span><span class="sxs-lookup"><span data-stu-id="b772a-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

