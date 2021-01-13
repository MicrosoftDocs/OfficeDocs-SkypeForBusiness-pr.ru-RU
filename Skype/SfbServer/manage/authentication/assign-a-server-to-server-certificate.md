---
title: Назначение сертификата проверки подлинности "сервер-сервер" Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: Сводка. Назначение сертификата проверки подлинности "сервер-сервер" для Skype для бизнеса Server.
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828509"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="fa33d-103">Назначение сертификата проверки подлинности "сервер-сервер" Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fa33d-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="fa33d-104">**Сводка:** Назначьте сертификат проверки подлинности "сервер-сервер" для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fa33d-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="fa33d-105">Чтобы определить, назначен ли сертификат проверки подлинности "сервер-сервер" skype для бизнеса Server, в командной командной оболочке Skype для бизнеса Server запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fa33d-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="fa33d-106">Если сведения о сертификате не возвращаются, необходимо назначить сертификат выдавливания маркеров, прежде чем можно будет использовать проверку подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="fa33d-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="fa33d-107">Как правило, любой сертификат Skype для бизнеса Server можно использовать в качестве сертификата OAuthTokenIssuer; Например, сертификат skype для бизнеса Server по умолчанию также можно использовать в качестве сертификата OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="fa33d-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fa33d-108">(Сертификат OAUthTokenIssuer также может быть любым сертификатом веб-сервера, который включает имя вашего домена SIP в поле "Тема".) К сертификату, используемому для проверки подлинности "сервер-сервер", предъявляются два основных требования: 1) один и тот же сертификат должен быть настроен как сертификат OAuthTokenIssuer на всех серверах переднего сервера; и 2) Сертификат должен быть не менее 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="fa33d-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="fa33d-109">Если у вас нет сертификата, который можно использовать для проверки подлинности "сервер-сервер", можно получить новый сертификат, импортировать новый сертификат и затем использовать его для проверки подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="fa33d-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="fa33d-110">После запроса и запроса нового сертификата можно войти на любой из серверов переднего Windows PowerShell для импорта и назначения этого сертификата с помощью команды Windows PowerShell, аналогичной этой:</span><span class="sxs-lookup"><span data-stu-id="fa33d-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="fa33d-111">В предыдущей команде параметр Path представляет полный путь к файлу сертификата, а параметр Password — пароль, который был назначен сертификату.</span><span class="sxs-lookup"><span data-stu-id="fa33d-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="fa33d-112">Эту процедуру следует выполнить только один раз: служба репликации Skype для бизнеса Server автоматически создаст набор запланированных задач, которые расшифровывают и развертывают сертификат на всех серверах переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="fa33d-113">Кроме того, можно использовать существующий сертификат в качестве сертификата проверки подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="fa33d-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="fa33d-114">(Как уже было отмечено, сертификат по умолчанию можно использовать в качестве сертификата проверки подлинности "сервер-сервер".) Следующая пара Windows PowerShell извлекает значение свойства Thumbprint сертификата по умолчанию, а затем использует это значение, чтобы сделать сертификат по умолчанию сертификатом проверки подлинности "сервер-сервер":</span><span class="sxs-lookup"><span data-stu-id="fa33d-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="fa33d-115">В предыдущей команде полученный сертификат настраивается для работы в качестве глобального сертификата проверки подлинности "сервер-сервер"; это означает, что сертификат будет реплицирован и использован всеми серверами переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="fa33d-116">Опять же, эту команду следует выполнить только один раз и только на одном из серверов переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="fa33d-117">Хотя все серверы переднего сервера должны использовать один и тот же сертификат, не следует настраивать сертификат OAuthTokenIssuer на каждом сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="fa33d-118">Вместо этого настройте сертификат один раз, а затем позвольте серверу репликации Skype для бизнеса Server копировать этот сертификат на каждый сервер.</span><span class="sxs-lookup"><span data-stu-id="fa33d-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="fa33d-119">Этот Set-CsCertificate принимает сертификат и сразу настраивает его в качестве текущего сертификата OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="fa33d-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="fa33d-120">(Skype для бизнеса Server сохраняет две копии типа сертификата: текущий и предыдущий.) Если требуется, чтобы новый сертификат сразу же начал действовать в качестве сертификата OAuthTokenIssuer, следует использовать Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="fa33d-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="fa33d-121">Вы также можете использовать Set-CsCertificate для "сверки" нового сертификата.</span><span class="sxs-lookup"><span data-stu-id="fa33d-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="fa33d-122">"Развертывание" сертификата просто означает, что новый сертификат должен стать текущим сертификатом OAuthTokenIssuer в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="fa33d-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="fa33d-123">Например, эта команда извлекает сертификат по умолчанию, а затем настраивает его для получения в качестве текущего сертификата OAuthTokenIssuer с 1 июля 2015 г.:</span><span class="sxs-lookup"><span data-stu-id="fa33d-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="fa33d-124">1 июля 2015 г. новый сертификат будет настроен как текущий сертификат OAuthTokenIssuer, а "старый" сертификат OAuthTokenIssuer — как предыдущий.</span><span class="sxs-lookup"><span data-stu-id="fa33d-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="fa33d-125">Если вы не хотите использовать Windows PowerShell вы также можете использовать консоль MMC "Сертификаты" для экспорта сертификата с одного сервера переднего сервера, а затем импортировать этот же сертификат на все остальные серверы переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="fa33d-126">В этом случае необходимо экспортировать закрытый ключ вместе с самим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="fa33d-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fa33d-127">В этом случае эту процедуру необходимо выполнить на каждом сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="fa33d-128">При экспорте и импорте сертификатов таким образом Skype для бизнеса Server не будет реплицировать этот сертификат на каждый сервер переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="fa33d-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="fa33d-129">После импорта сертификата на все серверы переднего Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa33d-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="fa33d-130">Чтобы назначить сертификат с помощью мастера развертывания, выполните следующие действия на компьютере, на котором установлен мастер развертывания:</span><span class="sxs-lookup"><span data-stu-id="fa33d-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="fa33d-131">Click Start, click All Programs, click **Skype for Business Server**, and then click Skype for Business Server Deployment **Wizard.**</span><span class="sxs-lookup"><span data-stu-id="fa33d-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="fa33d-132">В мастере развертывания щелкните "Установить или **обновить систему Skype для бизнеса Server".**</span><span class="sxs-lookup"><span data-stu-id="fa33d-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="fa33d-133">На странице Skype для бизнеса  Server нажмите кнопку "Выполнить" под заголовком **"Шаг 3. Запрос, установка или назначение сертификатов".**</span><span class="sxs-lookup"><span data-stu-id="fa33d-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="fa33d-134">(Примечание. Если вы уже установили сертификаты  на этом компьютере, кнопка "Выполнить" будет помечена как "Запустить **снова".)**</span><span class="sxs-lookup"><span data-stu-id="fa33d-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="fa33d-135">В мастере сертификатов выберите сертификат **OAuthTokenIssuer** и нажмите кнопку **"Назначить".**</span><span class="sxs-lookup"><span data-stu-id="fa33d-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="fa33d-136">В мастере назначения сертификатов на странице **"Назначение сертификатов"** нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fa33d-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="fa33d-137">На странице **"Хранилище** сертификатов" выберите сертификат, используемый для проверки подлинности "сервер-сервер", и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fa33d-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="fa33d-138">На странице Сводка по назначениям сертификатов щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="fa33d-139">На странице выполнения команд нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="fa33d-140">Закроем мастер сертификатов и мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="fa33d-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

