---
title: Мастер сертификатов
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Запрос, назначение, удалить, или просмотра сертификатов, используйте мастер сертификатов. Необходимо войти в систему с правами участника группы RTCUniversalServerAdmins. Для запроса сертификата из общедоступного центра сертификации не требуется участие в других группах. Чтобы запросить сертификат из вашей организации инфраструктуры открытого ключа (PKI), необходимо подтвердить, что дополнительные — при их наличии — членство в группах требуемых. Во время запроса на задачу можно ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата из инфраструктуры PKI в ЦС.
ms.openlocfilehash: d700a6cae510bbc12ed2e37c9c3df166d2704269
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-wizard"></a><span data-ttu-id="6cc09-107">Мастер сертификатов</span><span class="sxs-lookup"><span data-stu-id="6cc09-107">Certificate Wizard</span></span>
 
<span data-ttu-id="6cc09-108">В мастере сертификатов выполняются следующие операции с сертификатами: **Запрос**, **Назначить**, **Удалить** и **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="6cc09-109">Необходимо войти в систему с правами участника группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6cc09-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="6cc09-110">Для запроса сертификата из общедоступного центра сертификации не требуется участие в других группах.</span><span class="sxs-lookup"><span data-stu-id="6cc09-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="6cc09-111">Чтобы запросить сертификат из вашей организации инфраструктуры открытого ключа (PKI), необходимо подтвердить, что дополнительные — при их наличии — членство в группах требуемых.</span><span class="sxs-lookup"><span data-stu-id="6cc09-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="6cc09-112">Во время запроса на задачу можно ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата из инфраструктуры PKI в ЦС.</span><span class="sxs-lookup"><span data-stu-id="6cc09-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="6cc09-113">Для запроса нового сертификата нажмите кнопку **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="6cc09-114">Для назначения сертификата, который еще не назначен, нажмите кнопку **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="6cc09-115">Для удаления назначенного сертификата нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cc09-p103">Кнопка **Удалить** доступна только при наличии назначенного сертификата. Если кнопка **Удалить** отображается серым цветом и недоступна, ни один сертификат не назначен.</span><span class="sxs-lookup"><span data-stu-id="6cc09-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="6cc09-118">Для просмотра назначенного сертификата нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cc09-p104">Кнопка **Просмотреть** доступна только при наличии назначенного сертификата. Если кнопка **Просмотреть** отображается серым цветом и недоступна, ни один сертификат не назначен.</span><span class="sxs-lookup"><span data-stu-id="6cc09-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="6cc09-121">Для обновления текущего экрана назначения сертификатов нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="6cc09-122">Для импорта сертификата, отсутствующего в хранилище сертификатов, нажмите кнопку **Импорт сертификата**.</span><span class="sxs-lookup"><span data-stu-id="6cc09-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cc09-123">Функция **Импорт сертификата** обычно применяется при необходимости в обработке сертификата, полученного без формирования запроса в мастере сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6cc09-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="6cc09-124">Например, доступ к сертификату может быть предоставлен создавшим его администратором инфраструктуры открытых ключей.</span><span class="sxs-lookup"><span data-stu-id="6cc09-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="6cc09-125">Использование **Импортировать сертификат** , чтобы импортировать его на компьютер сертификат хранения и сделать его доступным для Скайп для Business Server для назначения.</span><span class="sxs-lookup"><span data-stu-id="6cc09-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="6cc09-p106">Если запрос сертификата из центра сертификации в организации требует утверждения администратором центра сертификации, для завершения процедуры запроса выберите **Обработать отложенный запрос**. Запрос сертификата возвращает состояние "отложен"; отображается также идентификационный номер отложенного запроса. Для продолжения обработки отложенного сертификата нажмите кнопку **Обновить**; при этом становится доступной кнопка **Обработать отложенный запрос**. Кнопка **Обработать отложенный запрос** больше не отображается серым цветом. Это делает возможной попытку извлечения отложенного запроса, но состояние "отложен" сохраняется до выпуска сертификата или отказа в его выпуске администратором центра сертификации. При отсутствии допустимых отложенных запросов, созданных с помощью мастера сертификатов, эта кнопка не доступна.</span><span class="sxs-lookup"><span data-stu-id="6cc09-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

