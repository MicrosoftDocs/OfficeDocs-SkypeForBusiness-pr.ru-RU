---
title: Запрос сертификата (возврат)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'На странице Состояние сетевого запроса сертификата предоставляется важная информация, появляющаяся в результате успешного создания и выдачи сетевого запроса сертификата. На этой странице отображается отпечаток сертификата, уникальным образом определяющий сертификат. По умолчанию этот сертификат назначается использованию сертификата Skype для бизнеса Server. Если нажать кнопку "Готово", сертификат будет автоматически назначен Lync Server 2013 для целей, определенных при создании запроса сертификата. По умолчанию сертификат назначается со следующими целями:'
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805149"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="9d7ea-107">Запрос сертификата (возврат)</span><span class="sxs-lookup"><span data-stu-id="9d7ea-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="9d7ea-108">На странице **Состояние сетевого запроса сертификата** предоставляется важная информация, появляющаяся в результате успешного создания и выдачи сетевого запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="9d7ea-109">На этой странице отображается отпечаток сертификата, уникальным образом определяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="9d7ea-110">По умолчанию этот сертификат назначается использованию сертификата Skype для бизнеса **Server.**</span><span class="sxs-lookup"><span data-stu-id="9d7ea-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="9d7ea-111">Если нажать кнопку **"Готово",** сертификат будет автоматически назначен Lync Server 2013 для целей, определенных при создании запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="9d7ea-112">По умолчанию сертификат назначается со следующими целями:</span><span class="sxs-lookup"><span data-stu-id="9d7ea-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="9d7ea-113">Сервер по умолчанию для MTLS — подключения к клиентам и другим серверам</span><span class="sxs-lookup"><span data-stu-id="9d7ea-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="9d7ea-114">Внутренние веб-службы — клиентские и серверные подключения на внутреннем сайте веб-служб для транспортного уровня безопасности/безопасного sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="9d7ea-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="9d7ea-115">Внешние веб-службы — клиентские и серверные подключения на сайте внешних веб-служб для TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="9d7ea-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="9d7ea-116">Щелкните **Просмотреть сведения о сертификате**, чтобы просмотреть сертификат и убедиться, что свойства сертификата соответствуют вашим целям и что сертификат готов к применению на сервере.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="9d7ea-117">Нажмите кнопку **Готово**, чтобы завершить процесс сетевого запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="9d7ea-118">Если вы выбрали этот сертификат для использования сертификатов Skype для бизнеса **Server,** сертификат назначается автоматически.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="9d7ea-119">Если вы решили снять флажок, необходимо вручную назначить сертификат на отдельном шаге.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9d7ea-120">Если выдавлив корневой сертификат ЦС нет в хранилище доверенных корневых ЦС компьютера или промежуточные сертификаты ЦС находятся в надлежащем хранилище, вы увидите сводное состояние, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="9d7ea-121">У вас нет возможности назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="9d7ea-122">Для завершения процесса назначения сертификата необходимо импортировать корневой сертификат выдающего ЦС и сертификаты промежуточных ЦС, а затем назначить сертификат, нажав кнопку **Назначить** на главной странице мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9d7ea-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

