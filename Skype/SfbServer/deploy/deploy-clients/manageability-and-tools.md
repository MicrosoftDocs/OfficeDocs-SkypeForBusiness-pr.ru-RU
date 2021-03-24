---
title: Управляемость и средства системы skype Room
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Ознакомьтесь с этой темой, чтобы узнать о средствах управления для системы номеров Skype.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093553"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="7afaf-103">Управляемость и средства системы skype Room</span><span class="sxs-lookup"><span data-stu-id="7afaf-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="7afaf-104">Ознакомьтесь с этой темой, чтобы узнать о средствах управления для системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="7afaf-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="7afaf-105">Портал администрирования</span><span class="sxs-lookup"><span data-stu-id="7afaf-105">Administrative Portal</span></span>

<span data-ttu-id="7afaf-106">Для локального развертывания Skype для бизнес-сервера можно использовать административный портал Skype Room System для активного управления развертыванием системы skype Room System в вашей организации и контроля за их развертыванием.</span><span class="sxs-lookup"><span data-stu-id="7afaf-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="7afaf-107">Дополнительные сведения см. в следующей статье:</span><span class="sxs-lookup"><span data-stu-id="7afaf-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="7afaf-108">Развертывание административного веб-портала SRS v1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7afaf-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="7afaf-109">Контрольный список Exchange</span><span class="sxs-lookup"><span data-stu-id="7afaf-109">Exchange Checklist</span></span>

- <span data-ttu-id="7afaf-110">Подтвердим, что автооткрытие настроено, а для autodiscover.domain.com доступна внутренняя запись DNS A/CNAME.</span><span class="sxs-lookup"><span data-stu-id="7afaf-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="7afaf-111">Автонаружение ping (например, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7afaf-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="7afaf-112">Проверьте свою службу автооткрытия с помощью средства анализатора подключения Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7afaf-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="7afaf-113">Выберите первый тест: "Я не могу войти в Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="7afaf-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="7afaf-114">Если в комнате собраний уже есть почтовый ящик ресурса, размести эту учетную запись для системы номеров Skype (пример сценария в нижней части страницы).</span><span class="sxs-lookup"><span data-stu-id="7afaf-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="7afaf-115">Контрольный список Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7afaf-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="7afaf-116">Запустите следующие средства:</span><span class="sxs-lookup"><span data-stu-id="7afaf-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="7afaf-117">Анализатор лучших практик Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7afaf-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="7afaf-118">Средство анализа состояния здоровья в Skype для бизнеса (Excel)</span><span class="sxs-lookup"><span data-stu-id="7afaf-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="7afaf-119">Анализатор подключения Skype для бизнеса 32-Bit или 64-Bit</span><span class="sxs-lookup"><span data-stu-id="7afaf-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="7afaf-120">Просмотрите полезные новые средства устранения [неполадок и анализа для Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="7afaf-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="7afaf-121">Подтвердим, что у вас есть пул Skype для бизнеса и сервер Office Web Apps и вы можете делиться колодой PowerPoint с помощью клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="7afaf-122">Если в комнате собраний уже есть почтовый ящик ресурса, впеть его для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="7afaf-123">При необходимости задай запрос did (номер телефона) для системы залов собраний и обнови поле "Общая телефонная связь" в средстве Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7afaf-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="7afaf-124">Сеть</span><span class="sxs-lookup"><span data-stu-id="7afaf-124">Network</span></span>

- <span data-ttu-id="7afaf-125">Убедитесь, что у вас есть проводное сетевое подключение для системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="7afaf-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="7afaf-126">Ознакомьтесь с руководством по планированию сети для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="7afaf-127">Запросить оценку сетевой сети Skype для бизнеса у партнера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="7afaf-128">Ознакомьтесь с данными о производительности, полученными в средстве анализа работоспособности Skype для бизнеса (Excel).</span><span class="sxs-lookup"><span data-stu-id="7afaf-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="7afaf-129">Запустите средство анализа сети.</span><span class="sxs-lookup"><span data-stu-id="7afaf-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="7afaf-130">Запустите средство диагностики предварительного вызова.</span><span class="sxs-lookup"><span data-stu-id="7afaf-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="7afaf-131">Системная безопасность skype Room</span><span class="sxs-lookup"><span data-stu-id="7afaf-131">Skype Room System Security</span></span>

<span data-ttu-id="7afaf-132">Skype Room System — это встроенная система, которая может быть полностью интегрирована в развертывание Windows с помощью модели безопасности Skype для бизнеса, управления правами и средств управления, таких как SCOM.</span><span class="sxs-lookup"><span data-stu-id="7afaf-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="7afaf-133">Поддерживаются перечисленные ниже возможности. </span><span class="sxs-lookup"><span data-stu-id="7afaf-133">Features include:</span></span>
  
- <span data-ttu-id="7afaf-134">Фильтр записи для предотвращения записи диска в пользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="7afaf-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="7afaf-135">Блокировка приложения для предотвращения запуска несанкционированных приложений.</span><span class="sxs-lookup"><span data-stu-id="7afaf-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="7afaf-136">Все usb-порты отключены в пользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="7afaf-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="7afaf-137">Стандартные приложения или телезрители не находятся на оборудовании Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7afaf-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="7afaf-138">Все содержимое отрисовка осуществляется с помощью протоколов HTTP или RDP.</span><span class="sxs-lookup"><span data-stu-id="7afaf-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="7afaf-139">На компьютере устройства работает операционная система Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="7afaf-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="7afaf-140">Все оборудование, включая устройства, предоставляется партнерами по OEM.</span><span class="sxs-lookup"><span data-stu-id="7afaf-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="7afaf-141">Необязательный доступ к доменным службам Active Directory (AD DS), что позволяет управлять учетной записью безопасности и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="7afaf-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="7afaf-142">Вы также можете управлять учетной записью местного администратора с помощью центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="7afaf-143">Система номеров Skype обновляется с помощью стандартных процессов обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7afaf-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="7afaf-144">Система номеров Skype подключается к Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="7afaf-145">Skype для бизнеса использует end-to-end шифрование и авторизацию для всех режимов связи</span><span class="sxs-lookup"><span data-stu-id="7afaf-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="7afaf-146">Система Номеров Skype поддерживает стандарты безопасности и соответствия требованиям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="7afaf-147">Дополнительные сведения см. в "Плане [безопасности" в Skype For Business Server.](../../plan-your-deployment/security/security.md)</span><span class="sxs-lookup"><span data-stu-id="7afaf-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="7afaf-148">Лицензия</span><span class="sxs-lookup"><span data-stu-id="7afaf-148">License</span></span>

<span data-ttu-id="7afaf-149">Убедитесь, что вы используете KMS для активации программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="7afaf-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="7afaf-150">Если это так, вам может потребоваться проверить или добавить ключ kmS клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="7afaf-151">Если вы не используете KMS, запросить ключ лицензирования тома для MAK клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="7afaf-152">Ключи лицензии</span><span class="sxs-lookup"><span data-stu-id="7afaf-152">License keys</span></span>

<span data-ttu-id="7afaf-153">В фоновом режиме skype Room System запускает настольный клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="7afaf-154">Если система номеров Skype является членом домена, она обнаружит ваш KMS.</span><span class="sxs-lookup"><span data-stu-id="7afaf-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="7afaf-155">(и если он имеет ключ KMS лицензирования тома, он активируется автоматически).</span><span class="sxs-lookup"><span data-stu-id="7afaf-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="7afaf-156">Лицензирование тома также предоставляет MAK, который вы вводите, когда он отображает xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="7afaf-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="7afaf-157">(Вам нужен доступ в Интернет, чтобы активировать с помощью MAK, но не KMS).</span><span class="sxs-lookup"><span data-stu-id="7afaf-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="7afaf-158">Дополнительные сведения см. в дополнительных сведениях об активации тома Office 2013.</span><span class="sxs-lookup"><span data-stu-id="7afaf-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="7afaf-159">Чтобы ввести ключ MAK, перейдите в средство лицензирования OEM Settings \> SRS.</span><span class="sxs-lookup"><span data-stu-id="7afaf-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="7afaf-160">Щелкните Проверить состояние .</span><span class="sxs-lookup"><span data-stu-id="7afaf-160">Click Check Status.</span></span> <span data-ttu-id="7afaf-161">Когда в состоянии написано "продукт не активирован", введите клавишу.</span><span class="sxs-lookup"><span data-stu-id="7afaf-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="7afaf-162">Если во время активации вы получите ошибку с сообщением "'Служба лицензирования программного обеспечения сообщила, что ключ продукта недействителен", убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="7afaf-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="7afaf-163">Клавиша была введена правильно.</span><span class="sxs-lookup"><span data-stu-id="7afaf-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="7afaf-164">Вы ввели ключ Skype для бизнеса MAK, а не другой ключ.</span><span class="sxs-lookup"><span data-stu-id="7afaf-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="7afaf-165">Система имеет доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="7afaf-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="7afaf-166">Вы можете активировать по телефону, но сначала должны были попытаться активировать с помощью средства лицензирования SRS.</span><span class="sxs-lookup"><span data-stu-id="7afaf-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="7afaf-167">Чтобы активировать по телефону, запустите тестовую встречу (не тестовый вызов, как слишком короткий).</span><span class="sxs-lookup"><span data-stu-id="7afaf-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="7afaf-168">В мастере активации Office выберите активацию телефона, позвоните в Корпорацию Майкрософт, введите длинный номер и введите ответ.</span><span class="sxs-lookup"><span data-stu-id="7afaf-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="7afaf-169">Управление сертификатами</span><span class="sxs-lookup"><span data-stu-id="7afaf-169">Certificate Authority</span></span>

<span data-ttu-id="7afaf-170">Подтверждение того, что орган сертификации, используемый для выдачи сертификата Office Web Apps Server 2013, имеет путь HTTP, включенный в свойство Списка отзывов сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7afaf-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="7afaf-171">Импорт файла сертификата (.crt) в систему skype Room System при использовании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7afaf-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="7afaf-172">Его легко получить из доли CertEnroll на сервере CA или в папке Доверенный корневой сервер любого домена, присоединяемого к КОМПЬЮТЕРУ.</span><span class="sxs-lookup"><span data-stu-id="7afaf-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="7afaf-173">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="7afaf-173">Certificates</span></span>

<span data-ttu-id="7afaf-174">Убедитесь, что в вашем органе сертификации есть http-путь для списка отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7afaf-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="7afaf-175">Если нет, обновите свой ЦС, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="7afaf-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="7afaf-176">Установите сертификаты в установке администратора системы номеров Skype в диспетчере сертификатов system \> Settings.</span><span class="sxs-lookup"><span data-stu-id="7afaf-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="7afaf-177">Для внутреннего сертификата необходим корпоративный корневой ЦС.</span><span class="sxs-lookup"><span data-stu-id="7afaf-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="7afaf-178">Один из способов получения необходимых сертификатов — открыть ЦС, выдав сертификаты.</span><span class="sxs-lookup"><span data-stu-id="7afaf-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="7afaf-179">Для Skype для бизнеса Server на компьютере в Skype для бизнеса щелкните Параметры средств набора \> \> параметров конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7afaf-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="7afaf-180">Это открывает веб-страницу, защищенную ЦС, выдав внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="7afaf-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="7afaf-181">Щелкните значок Блокировка на панели адресов браузера, чтобы отобразить отчет о безопасности.</span><span class="sxs-lookup"><span data-stu-id="7afaf-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="7afaf-182">Щелкните Просмотреть сертификаты и изучить свойство точки распространения CRL.</span><span class="sxs-lookup"><span data-stu-id="7afaf-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="7afaf-183">Вторым параметром CN должно быть имя сервера ЦС.</span><span class="sxs-lookup"><span data-stu-id="7afaf-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="7afaf-184">Теперь откройте Обозреватель Windows для этого \\ \< CA Server Name \> адреса \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="7afaf-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="7afaf-185">Скопируйте два файла .crl и файл .crt на флэш-накопитель и поместите его в левую сторону доски SMART.</span><span class="sxs-lookup"><span data-stu-id="7afaf-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="7afaf-186">Импорт файла .crt в систему Номеров Skype в папке Доверенный орган сертификации комнат.</span><span class="sxs-lookup"><span data-stu-id="7afaf-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="7afaf-187">Импорт файлов .crl в системе номеров Skype в папке Промежуточные органы сертификации.</span><span class="sxs-lookup"><span data-stu-id="7afaf-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="7afaf-188">(Чтобы увидеть файлы, необходимо изменить фильтр расширения файлов в диспетчере сертификатов на .crl).</span><span class="sxs-lookup"><span data-stu-id="7afaf-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="7afaf-189">Примечание. Сервер Office Web Apps 2013 может иметь тот же ЦС, что и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7afaf-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="7afaf-190">Если этого не сделать, вы не сможете поделиться PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="7afaf-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="7afaf-191">Ознакомьтесь с ИТ-файлами и получите CRT и CRL-файлы из сетевой доли Ca CertEnroll, как было объяснено выше.</span><span class="sxs-lookup"><span data-stu-id="7afaf-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="7afaf-192">Членство в домене может упростить некоторые вещи, так как система номеров Skype может рассматриваться как система Windows, и она может полагаться на Active Directory для некоторых аспектов сертификата.</span><span class="sxs-lookup"><span data-stu-id="7afaf-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="7afaf-193">Тем не менее, лучше вручную управлять этим.</span><span class="sxs-lookup"><span data-stu-id="7afaf-193">However, it's best to manually manage this.</span></span>
