---
title: Мастер сертификатов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: В мастере сертификатов можно Запросить, Назначить, Удалить или Просмотреть сертификаты. Вы должны войти как участник группы RTCUniversalServerAdmins. Для запроса сертификата из общего центра сертификации необходимо дополнительное участие в группах. Чтобы запросить сертификат из инфраструктуры открытых ключей (PKI) вашей организации, необходимо подтвердить, какие дополнительные (если они есть) членство в группах вам потребуется. Во время задачи запроса можно ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата из вашего ЦС PKI.
ms.openlocfilehash: 21ffd71ab649892b912d139afe5cd295ef5fec61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801729"
---
# <a name="certificate-wizard"></a><span data-ttu-id="3cdfe-107">Мастер сертификатов</span><span class="sxs-lookup"><span data-stu-id="3cdfe-107">Certificate Wizard</span></span>
 
<span data-ttu-id="3cdfe-108">В мастере сертификатов можно **Запросить**, **Назначить**, **Удалить** или **Просмотреть** сертификаты.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="3cdfe-109">Вы должны войти как участник группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="3cdfe-110">Для запроса сертификата из общего центра сертификации необходимо дополнительное участие в группах.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="3cdfe-111">Чтобы запросить сертификат из инфраструктуры открытых ключей (PKI) вашей организации, необходимо подтвердить, какие дополнительные (если они есть) членство в группах вам потребуется.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="3cdfe-112">Во время задачи запроса можно ввести альтернативные учетные данные, которые будут использоваться для запроса сертификата из вашего ЦС PKI.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="3cdfe-113">Чтобы запросить новый сертификат, нажмите кнопку **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="3cdfe-114">Чтобы назначить еще не назначенный сертификат, нажмите кнопку **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="3cdfe-115">Чтобы удалить ранее назначенный сертификат, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cdfe-p103">Кнопка **Удалить** доступна только при наличии ранее назначенного сертификата. Если кнопка **Удалить** недоступна (неактивна), назначенного сертификата нет.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="3cdfe-118">Чтобы просмотреть назначенный сертификат, нажмите кнопку **Просмотреть**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cdfe-p104">Кнопка **Просмотреть** доступна только при наличии ранее назначенного сертификата. Если кнопка **Просмотреть** неактивна, назначенного сертификата нет.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="3cdfe-121">Чтобы обновить текущий экран назначения сертификата, нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="3cdfe-122">Чтобы импортировать сертификат, которого нет в хранилище сертификатов, щелкните **Импорт сертификата**.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cdfe-123">Функция **Импорт сертификата** обычно используется для обработки сертификата, полученного вне запроса из мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="3cdfe-124">Например, ваш администратор инфраструктуры открытых ключей создает сертификат и делает его доступным для вас.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="3cdfe-125">Используйте **импорт сертификата,** чтобы импортировать сертификат в хранилище сертификатов компьютера и сделать его доступным для назначения Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="3cdfe-p106">Чтобы завершить процесс запроса сертификата, требующего утверждения администратором, из центра сертификации вашей организации, щелкните **Обработать отложенный запрос**. По запросу сертификата возвращается состояние "отложенный", отображается также идентификационный номер отложенного запроса. Чтобы продолжить обработку отложенного сертификата, нажмите кнопку **Обновить**, чтобы активировать кнопку **Обработать отложенный запрос**. Кнопка **Обработать отложенный запрос** станет доступной (активной). Вы можете затем попытаться вернуть отложенный запрос, но запрос сохранит состояние отложенного вплоть до выдачи сертификата или отклонения запроса администратором центра сертификации. Кнопка будет недоступна при отсутствии допустимых отложенных запросов, созданных мастером сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3cdfe-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

