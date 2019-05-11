---
title: Запрос сертификата (возврат)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'Страница состояние запроса на сертификат содержит важные сведения, которые являются результатом успешного создания и выполнения запроса на сертификат через Интернет. На этой странице представлены отпечаток сертификата, который уникальным образом определяет сертификат. По умолчанию установлен флажок назначить этот сертификат Скайп для использования сертификата сервера. Если нажать кнопку Готово, сертификат будет автоматически назначен Скайп для Business Server в целях, заданных во время создания действия запроса на сертификат. По умолчанию в целях, будет назначен сертификат являются:'
ms.openlocfilehash: f9d4094cb42690dfc6db252cbd8d7ad82fbab2a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893905"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="9c158-107">Запрос сертификата (возврат)</span><span class="sxs-lookup"><span data-stu-id="9c158-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="9c158-108">Страница **Состояние запроса на сертификат** содержит важные сведения, которые являются результатом успешного создания и выполнения запроса на сертификат через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9c158-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="9c158-109">На этой странице представлены отпечаток сертификата, который уникальным образом определяет сертификат.</span><span class="sxs-lookup"><span data-stu-id="9c158-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="9c158-110">По умолчанию установлен флажок, **Назначение сертификата для Скайп для использования сертификата сервера** .</span><span class="sxs-lookup"><span data-stu-id="9c158-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="9c158-111">Если нажать кнопку **Готово**, сертификат будет автоматически назначен Скайп для Business Server в целях, заданных во время создания действия запроса на сертификат.</span><span class="sxs-lookup"><span data-stu-id="9c158-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="9c158-112">По умолчанию в целях, будет назначен сертификат являются:</span><span class="sxs-lookup"><span data-stu-id="9c158-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="9c158-113">Сервер по умолчанию для взаимной транспортного уровня безопасности (MTLS) - соединения с клиентами и другими серверами</span><span class="sxs-lookup"><span data-stu-id="9c158-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="9c158-114">Внутренние - соединения клиентов и серверов на внутренний веб-сайте служб для транспортного уровня безопасности/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="9c158-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="9c158-115">Веб-служб внешних - соединения клиентов и серверов на внешний веб-сайте служб для TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="9c158-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="9c158-116">Нажмите кнопку **Просмотр сведений о сертификате** , чтобы просмотреть сертификат, чтобы подтвердить, что свойства сертификата введены правильно, и, что сертификат готова к применен и использованием на сервере.</span><span class="sxs-lookup"><span data-stu-id="9c158-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="9c158-117">Нажмите кнопку **Готово** для завершения процесса запроса на сертификат через Интернет.</span><span class="sxs-lookup"><span data-stu-id="9c158-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="9c158-118">Если выбран флажок **Назначение сертификата для Скайп для использования сертификата Business Server**, сертификат будет автоматически назначается.</span><span class="sxs-lookup"><span data-stu-id="9c158-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="9c158-119">Если флажок не установлен, необходимо назначить сертификат отдельно.</span><span class="sxs-lookup"><span data-stu-id="9c158-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9c158-120">Если выдающего корневой сертификат центром сертификации (ЦС) не входит в хранилище доверенного корневого центра сертификации или если промежуточного ЦС не соответствующие хранилища, вы увидите сводки состояния, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="9c158-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="9c158-121">Вы не можете назначение сертификата.</span><span class="sxs-lookup"><span data-stu-id="9c158-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="9c158-122">Чтобы завершить процесс назначения сертификата, необходимо импортировать корневой сертификат и любого промежуточного ЦС и затем назначение сертификата, щелкнув **Назначение** на главной странице мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9c158-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

