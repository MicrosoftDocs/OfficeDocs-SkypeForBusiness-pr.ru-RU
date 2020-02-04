---
title: Запрос сертификата (возврат)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'На странице состояния запроса онлайнового сертификата отображаются важные сведения, полученные в результате успешного создания и выпуска запроса на онлайновый сертификат. На этой странице представлена отпечаток сертификата, который однозначно определяет сертификат. По умолчанию этот флажок назначает этот сертификат для использования сертификата Skype для Business Server. После нажатия кнопки "Готово" сертификат будет автоматически назначаться в Skype для бизнеса Server для целей, определенных в ходе создания запроса сертификата. По умолчанию для назначения сертификата используются следующие назначения:'
ms.openlocfilehash: 0afc23baacc3430edaf1868e9fbe22e2e04455d7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705614"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="39340-107">Запрос сертификата (возврат)</span><span class="sxs-lookup"><span data-stu-id="39340-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="39340-108">На странице **состояния запроса онлайнового сертификата** отображаются важные сведения, полученные в результате успешного создания и выпуска запроса на онлайновый сертификат.</span><span class="sxs-lookup"><span data-stu-id="39340-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="39340-109">На этой странице представлена отпечаток сертификата, который однозначно определяет сертификат.</span><span class="sxs-lookup"><span data-stu-id="39340-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="39340-110">По умолчанию **этот флажок назначает этот сертификат для использования сертификата Skype для Business Server** .</span><span class="sxs-lookup"><span data-stu-id="39340-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="39340-111">После нажатия кнопки **"Готово"** сертификат будет автоматически назначаться в Skype для бизнеса Server для целей, определенных в ходе создания запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="39340-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="39340-112">По умолчанию для назначения сертификата используются следующие назначения:</span><span class="sxs-lookup"><span data-stu-id="39340-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="39340-113">Сервер по умолчанию для взаимной защиты транспортного уровня (MTLS) — подключение к клиентам и другим серверам</span><span class="sxs-lookup"><span data-stu-id="39340-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="39340-114">Внутренние серверные и клиентские соединения веб-служб на внутреннем сайте веб-служб для обеспечения безопасности транспортного уровня (TLS/SSL).</span><span class="sxs-lookup"><span data-stu-id="39340-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="39340-115">Внешние веб-службы — соединение с клиентом и сервером на внешнем сайте веб-служб TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="39340-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="39340-116">Щелкните ссылку **Просмотр сведений о сертификате** , чтобы просмотреть сертификат, чтобы убедиться, что свойства сертификата предназначены для вашего назначения, и что сертификат готов к применению и используется на сервере.</span><span class="sxs-lookup"><span data-stu-id="39340-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="39340-117">Нажмите кнопку **Готово** , чтобы завершить процесс запроса онлайнового сертификата.</span><span class="sxs-lookup"><span data-stu-id="39340-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="39340-118">Если вы установили флажок **назначать этот сертификат для использования сертификата Skype для Business Server**, сертификат будет автоматически назначен.</span><span class="sxs-lookup"><span data-stu-id="39340-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="39340-119">Если вы решили снять этот флажок, необходимо назначить сертификат на отдельном этапе.</span><span class="sxs-lookup"><span data-stu-id="39340-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39340-120">Если корневой сертификат центра сертификации (ЦС) не находится в хранилище доверенных корневых центров сертификации компьютера или если сертификаты промежуточных центров сертификации не находятся в нужном хранилище, отобразится сводное состояние, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="39340-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="39340-121">У вас нет возможности назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="39340-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="39340-122">Чтобы завершить процесс назначения сертификата, необходимо импортировать корневой сертификат центра сертификации и все промежуточные сертификаты ЦС, а затем назначить сертификат, нажав кнопку **назначить** на главной странице мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="39340-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

