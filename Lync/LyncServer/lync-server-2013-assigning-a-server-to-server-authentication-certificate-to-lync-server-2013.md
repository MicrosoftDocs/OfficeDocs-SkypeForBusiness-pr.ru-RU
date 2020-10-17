---
title: Назначение сертификата проверки подлинности между серверами в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec8ac614cdc829ab2b1efd7d6ff9179c33d5a33e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499476"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="74a8b-102">Назначение сертификата проверки подлинности между серверами серверу Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74a8b-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74a8b-103">_**Последнее изменение темы:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="74a8b-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="74a8b-104">Чтобы определить, был ли сертификат проверки подлинности "сервер – сервер" уже назначен Microsoft Lync Server 2013, выполните следующую команду в командной консоли Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="74a8b-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="74a8b-105">Если сведения о сертификате не возвращаются, необходимо назначить сертификат поставщика маркеров, прежде чем использовать проверку подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="74a8b-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="74a8b-106">Как правило, любой сертификат Lync Server 2013 можно использовать в качестве сертификата OAuthTokenIssuer. Например, сертификат по умолчанию для Lync Server 2013 также можно использовать в качестве сертификата OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="74a8b-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="74a8b-107">(Сертификат OAUthTokenIssuer также может представлять собой любой сертификат веб-сервера, включающий в себя имя домена SIP в поле subject (субъект).) Основные два требования к сертификату, используемому для проверки подлинности "сервер-сервер": 1) один и тот же сертификат должен быть настроен как сертификат OAuthTokenIssuer на всех серверах переднего плана; и 2) сертификат должен иметь по крайней мере 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="74a8b-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="74a8b-108">Если у вас нет сертификата, который можно использовать для межсерверной проверки подлинности, вы можете получить новый сертификат, импортировать новый сертификат, а затем использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="74a8b-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="74a8b-109">После того как вы запрашиваете и получаете новый сертификат, вы можете войти на любой из серверов переднего плана и использовать команду Windows PowerShell, аналогичную следующей, для импорта и назначения этого сертификата:</span><span class="sxs-lookup"><span data-stu-id="74a8b-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="74a8b-110">В предыдущей команде параметр path представляет полный путь к файлу сертификата, а параметр Password — пароль, назначенный сертификату.</span><span class="sxs-lookup"><span data-stu-id="74a8b-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="74a8b-111">Эту процедуру следует выполнять только один раз: служба репликации Lync Server будет автоматически создавать набор запланированных задач, которые будут расшифровывать и развертывать сертификат на все серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="74a8b-112">Кроме того, вы можете использовать существующий сертификат в качестве сертификата проверки подлинности "сервер – сервер".</span><span class="sxs-lookup"><span data-stu-id="74a8b-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="74a8b-113">(Как отмечено, сертификат по умолчанию можно использовать в качестве сертификата проверки подлинности "сервер-сервер".) Следующая комбинация команд Windows PowerShell извлекает значение свойства Thumbprint сертификата по умолчанию, а затем использует это значение для создания сертификата проверки подлинности "сервер – сервер" по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="74a8b-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="74a8b-114">В предыдущей команде полученный сертификат настраивается для работы в качестве глобального сертификата проверки подлинности "сервер-сервер"; Это означает, что сертификат будет реплицирован на все серверы переднего плана и использоваться им.</span><span class="sxs-lookup"><span data-stu-id="74a8b-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="74a8b-115">Опять же, эта команда должна выполняться только один раз и только на одном из серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="74a8b-116">Несмотря на то, что на всех серверах переднего плана должен использоваться один и тот же сертификат, не следует настраивать сертификат OAuthTokenIssuer на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="74a8b-117">Вместо этого необходимо настроить сертификат один раз, а затем позволить серверу репликации Lync Server выполнить копирование этого сертификата на каждый сервер.</span><span class="sxs-lookup"><span data-stu-id="74a8b-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="74a8b-118">Командлет Set-CsCertificate берет на себя сертификат и сразу же настраивает этот сертификат в качестве текущего сертификата OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="74a8b-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="74a8b-119">(Lync Server 2013 хранит две копии типа сертификата: текущий сертификат и предыдущий сертификат). Если требуется, чтобы новый сертификат сразу начал работать в качестве сертификата OAuthTokenIssuer, следует использовать командлет Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="74a8b-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="74a8b-120">Вы также можете использовать командлет Set-CsCertificate для "свертывания" нового сертификата.</span><span class="sxs-lookup"><span data-stu-id="74a8b-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="74a8b-121">"Пошаговое" сертификат означает, что новый сертификат будет настроен в качестве текущего сертификата OAuthTokenIssuer в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="74a8b-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="74a8b-122">Например, эта команда получает сертификат по умолчанию, а затем настраивает этот сертификат для использования в качестве текущего сертификата OAuthTokenIssuer на 1 июля 2012 г.:</span><span class="sxs-lookup"><span data-stu-id="74a8b-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="74a8b-123">На 1 июля 2012 новый сертификат будет настроен как текущий сертификат OAuthTokenIssuer, а "старый" сертификат OAuthTokenIssuer будет настроен как предыдущий сертификат.</span><span class="sxs-lookup"><span data-stu-id="74a8b-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="74a8b-124">Если вы не хотите использовать Windows PowerShell, вы также можете экспортировать сертификат с одного сервера переднего плана с помощью консоли MMC для сертификатов, а затем импортировать этот же сертификат на все другие серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="74a8b-125">В этом случае необходимо экспортировать закрытый ключ вместе с самим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="74a8b-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="74a8b-126">В этом случае процедуру необходимо выполнить на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="74a8b-127">При экспорте и импорте сертификатов таким образом Lync Server 2013 не будет реплицировать этот сертификат на каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74a8b-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="74a8b-128">После импорта сертификата на все серверы переднего плана этот сертификат можно назначить с помощью мастера развертывания Lync Server, а не Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74a8b-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="74a8b-129">Чтобы назначить сертификат с помощью мастера развертывания, выполните следующие действия на компьютере, на котором установлен мастер развертывания:</span><span class="sxs-lookup"><span data-stu-id="74a8b-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="74a8b-130">Нажмите кнопку Пуск, последовательно выберите пункты Все программы, **Microsoft Lync server 2013**и **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="74a8b-131">В мастере развертывания щелкните **Установить или обновить Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="74a8b-132">На странице Microsoft Lync Server 2013 нажмите кнопку **выполнить** под заголовком **Шаг 3: запрос, установка или назначение сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="74a8b-133">(Примечание: Если вы уже установили сертификаты на этом компьютере, кнопка **выполнить** будет помечена **снова**.)</span><span class="sxs-lookup"><span data-stu-id="74a8b-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="74a8b-134">В мастере сертификатов выберите сертификат **OAuthTokenIssuer** , а затем нажмите кнопку **назначить**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="74a8b-135">В мастере назначения сертификатов на странице **назначение сертификата** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="74a8b-136">На странице **хранилище сертификатов** выберите сертификат, который будет использоваться для проверки подлинности "сервер-сервер", а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="74a8b-137">На странице Сводка по назначениям сертификатов щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="74a8b-138">На странице выполнения команд нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="74a8b-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="74a8b-139">Закройте мастер сертификатов и мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="74a8b-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

