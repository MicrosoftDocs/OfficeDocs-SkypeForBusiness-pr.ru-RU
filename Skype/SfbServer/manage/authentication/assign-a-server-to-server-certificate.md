---
title: Назначение сертификата для проверки подлинности серверов и серверов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Сводка: назначьте сертификат проверки подлинности серверов на сервер для Skype для бизнеса Server.'
ms.openlocfilehash: 4689306e0fb8cd7b7c8ce67f74c6ddb65db44f13
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818861"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="a4825-103">Назначение сертификата для проверки подлинности серверов и серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a4825-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="a4825-104">**Сводка:** Назначьте сертификат для проверки подлинности серверов и серверов для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a4825-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="a4825-105">Чтобы определить, назначен ли сертификат проверки подлинности сервера серверу Skype для бизнеса Server, выполните следующую команду в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="a4825-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="a4825-106">Если сведения о сертификате не возвращаются, для проверки подлинности между серверами необходимо сначала назначить сертификат издателя маркеров.</span><span class="sxs-lookup"><span data-stu-id="a4825-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="a4825-107">Как правило, в качестве сертификата Оаустокениссуер можно использовать любой сертификат Skype для бизнеса Server. Например, сертификат по умолчанию в Skype для бизнеса Server также можно использовать в качестве сертификата Оаустокениссуер.</span><span class="sxs-lookup"><span data-stu-id="a4825-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a4825-108">(Сертификат Оаустокениссуер также может представлять собой любой сертификат веб-сервера, включающий имя вашего домена SIP в поле субъекта.) Ниже указаны основные требования к сертификату, используемому для проверки подлинности серверов и сервера: 1) один и тот же сертификат должен быть настроен как сертификат Оаустокениссуер на всех серверах переднего плана; и 2) сертификат должен составлять не менее 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="a4825-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="a4825-109">При отсутствии сертификата, позволяющего проверять подлинность между серверами, можно получить новый сертификат, импортировать его и затем применять для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="a4825-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="a4825-110">После запроса и получения нового сертификата вы можете войти на любой из своих серверов переднего плана и с помощью команды Windows PowerShell, аналогичной этой, для импорта и назначения этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="a4825-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="a4825-111">В предыдущей команде параметр Path представляет полный путь к файлу сертификата, а параметр Password – пароль, назначенный сертификату.</span><span class="sxs-lookup"><span data-stu-id="a4825-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="a4825-112">Эту процедуру необходимо выполнить только один раз: служба репликации в Skype для бизнеса Server автоматически создаст набор запланированных задач, которые будут расшифровывать и развертывать сертификат на всех серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="a4825-113">Можно также задать в качестве сертификата проверки подлинности между серверами существующий сертификат.</span><span class="sxs-lookup"><span data-stu-id="a4825-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="a4825-114">(Как отмечено, сертификат по умолчанию можно использовать в качестве сертификата для проверки подлинности сервера и сервера.) В следующей паре команд Windows PowerShell извлекается значение свойства Thumbprint сертификата по умолчанию, а затем используйте это значение, чтобы сделать сертификат по умолчанию сертификатом проверки подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="a4825-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="a4825-115">В предыдущей команде полученный сертификат настроен для функционирования глобального сертификата проверки подлинности серверов и серверов; Это означает, что сертификат будет реплицирован и использоваться всеми серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="a4825-116">Эту команду можно выполнить только один раз и только на одном из ваших серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="a4825-117">Несмотря на то, что все серверы переднего плана должны использовать один и тот же сертификат, не следует настраивать сертификат Оаустокениссуер на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="a4825-118">Вместо этого настройте сертификат один раз, чтобы сервер репликации Skype для бизнеса Server мог следить за копированием этого сертификата на каждый сервер.</span><span class="sxs-lookup"><span data-stu-id="a4825-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="a4825-119">Командлет Set-Ксцертификате берет на вопрос сертификат и сразу же настраивает этот сертификат для использования в качестве текущего сертификата Оаустокениссуер.</span><span class="sxs-lookup"><span data-stu-id="a4825-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a4825-120">(В Skype для бизнеса Server существуют две копии типа сертификата: текущий сертификат и предыдущий сертификат.) Если вам нужно сразу же приступить к работе с новым сертификатом в качестве сертификата Оаустокениссуер, следует использовать командлет Set-Ксцертификате.</span><span class="sxs-lookup"><span data-stu-id="a4825-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="a4825-p107">Можно также воспользоваться командлетом Set-CsCertificate, чтобы "накатить" новый сертификат. "Накат" означает, что новый сертификат станет текущим сертификатом OAuthTokenIssuer в некоторый определенный момент времени. Например, следующая команда извлекает сертификат по умолчанию и затем делает так, что он становится текущим сертификатом OAuthTokenIssuer 1 июля 2015 г.:</span><span class="sxs-lookup"><span data-stu-id="a4825-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="a4825-124">На 1 июля 2015 новый сертификат будет настроен в качестве текущего сертификата Оаустокениссуер и сертификат Оаустокениссуер "старый" будет настроен как предыдущий сертификат.</span><span class="sxs-lookup"><span data-stu-id="a4825-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="a4825-125">Если вы не хотите использовать Windows PowerShell, вы также можете экспортировать сертификат с первого сервера переднего плана с помощью консоли MMC "сертификаты", а затем импортировать этот же сертификат на все другие серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="a4825-126">При этом вместе с сертификатом необходимо экспортировать закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="a4825-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a4825-127">В этом случае процедура должна выполняться на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="a4825-128">При таком способе экспорта и импорта сертификатов в Skype для бизнеса Server не будет реплицировать этот сертификат на каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a4825-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="a4825-129">После импорта сертификата на все серверы переднего плана этот сертификат может быть назначен с помощью мастера развертывания Skype для бизнеса Server вместо Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4825-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="a4825-130">Для назначения сертификата с помощью мастера развертывания выполните следующие действия на компьютере, где установлен мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4825-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="a4825-131">Нажмите кнопку Пуск, выберите пункт Все программы, а затем — **Skype для бизнеса Server**, а затем — **Мастер развертывания Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a4825-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="a4825-132">В мастере развертывания нажмите кнопку **Установка или обновление системы Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a4825-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="a4825-133">На странице Skype для бизнеса Server нажмите кнопку **выполнить** под заголовком **Шаг 3: запрос, установка и назначение сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="a4825-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="a4825-134">(Примечание. Если вы уже установили сертификаты на этом компьютере, нажмите кнопку " **выполнить** ", чтобы пометить **ее.)**</span><span class="sxs-lookup"><span data-stu-id="a4825-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="a4825-135">В мастере сертификатов выберите сертификат **OAuthTokenIssuer**, затем нажмите кнопку **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="a4825-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="a4825-136">В мастере назначения сертификатов на странице **Назначение сертификатов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4825-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="a4825-137">На странице **Хранилище сертификатов** выберите сертификат для применения при проверке подлинности между серверами, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4825-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="a4825-138">На странице "Сводка по назначениям сертификатов" нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4825-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="a4825-139">На странице "Выполнение команд" нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a4825-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="a4825-140">Закройте мастер сертификатов и мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="a4825-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

