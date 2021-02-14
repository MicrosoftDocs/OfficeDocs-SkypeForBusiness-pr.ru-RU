---
title: Управление системой комнат Skype и инструменты
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
description: В этом разделе вы узнаете о средствах управления для системы комнат Skype.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805799"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="e7930-103">Управление системой комнат Skype и инструменты</span><span class="sxs-lookup"><span data-stu-id="e7930-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="e7930-104">В этом разделе вы узнаете о средствах управления для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7930-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="e7930-105">Портал администрирования</span><span class="sxs-lookup"><span data-stu-id="e7930-105">Administrative Portal</span></span>

<span data-ttu-id="e7930-106">Для локального развертывания Skype для бизнеса Server можно использовать портал администрирования системы комнат Skype для активного управления развертываниями системы комнат Skype в организации и отслеживания их развертывания.</span><span class="sxs-lookup"><span data-stu-id="e7930-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="e7930-107">Дополнительные сведения см. в следующей статье:</span><span class="sxs-lookup"><span data-stu-id="e7930-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="e7930-108">Развертывание веб-портала администрирования SRS 1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e7930-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="e7930-109">Контрольный список Exchange</span><span class="sxs-lookup"><span data-stu-id="e7930-109">Exchange Checklist</span></span>

- <span data-ttu-id="e7930-110">Подтвердим, что автооружие настроено, и для autodiscover.domain.com доступна внутренняя запись DNS A/CNAME.</span><span class="sxs-lookup"><span data-stu-id="e7930-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="e7930-111">Автооружение Ping (например, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e7930-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="e7930-112">Протестировать службу автооружия с помощью анализатора подключений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e7930-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="e7930-113">Выберите первый тест "Не могу войти в Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="e7930-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="e7930-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span><span class="sxs-lookup"><span data-stu-id="e7930-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="e7930-115">Контрольный список Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e7930-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="e7930-116">Запустите следующие средства:</span><span class="sxs-lookup"><span data-stu-id="e7930-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="e7930-117">Анализатор лучших методик Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e7930-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="e7930-118">Средство анализа состояния Skype для бизнеса (Excel)</span><span class="sxs-lookup"><span data-stu-id="e7930-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="e7930-119">32-битный или 64-битный анализатор подключений Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e7930-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="e7930-120">Просмотрите [полезные новые средства устранения неполадок и анализа для Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)</span><span class="sxs-lookup"><span data-stu-id="e7930-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="e7930-121">Подтвердим, что у вас есть пул Skype для бизнеса и сервер Office Web Apps, и вы можете совместно использовать колоду PowerPoint с помощью клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="e7930-122">Если в комнате для собраний уже есть почтовый ящик ресурса, в качестве его можно использовать Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="e7930-123">При необходимости запросим did (номер телефона) для системы комнат переговоров и обновим поле "Общий телефон" в средстве Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e7930-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="e7930-124">Сеть</span><span class="sxs-lookup"><span data-stu-id="e7930-124">Network</span></span>

- <span data-ttu-id="e7930-125">Убедитесь, что у вас есть проводное сетевое подключение для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7930-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="e7930-126">Ознакомьтесь с руководством по планированию сети для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="e7930-127">Запросить оценку сети Skype для бизнеса у партнера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="e7930-128">Прочитайте данные о производительности, полученные в средстве анализа работоспособности Skype для бизнеса (Excel).</span><span class="sxs-lookup"><span data-stu-id="e7930-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="e7930-129">Запустите средство анализа сети.</span><span class="sxs-lookup"><span data-stu-id="e7930-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="e7930-130">Запустите средство диагностики перед вызовом.</span><span class="sxs-lookup"><span data-stu-id="e7930-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="e7930-131">Безопасность системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="e7930-131">Skype Room System Security</span></span>

<span data-ttu-id="e7930-132">Система комнат Skype — это встроенная система, которая может быть полностью интегрирована в развертывание Windows с помощью модели безопасности Skype для бизнеса, управления правами и средств управления, таких как SCOM.</span><span class="sxs-lookup"><span data-stu-id="e7930-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="e7930-133">Поддерживаются перечисленные ниже возможности. </span><span class="sxs-lookup"><span data-stu-id="e7930-133">Features include:</span></span>
  
- <span data-ttu-id="e7930-134">Фильтр записи для предотвращения записи диска в пользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="e7930-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="e7930-135">Блокировка приложений для предотвращения запуска несанкционированных приложений.</span><span class="sxs-lookup"><span data-stu-id="e7930-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="e7930-136">Все USB-порты отключены в пользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="e7930-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="e7930-137">На оборудовании системы комнат Skype нет стандартных приложений или средств просмотра.</span><span class="sxs-lookup"><span data-stu-id="e7930-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="e7930-138">Весь контент отрисовка осуществляется по протоколам HTTP или RDP.</span><span class="sxs-lookup"><span data-stu-id="e7930-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="e7930-139">На компьютере устройства работает операционная система Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="e7930-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="e7930-140">Все оборудование, включая устройства, предоставляется партнерами по OEM.</span><span class="sxs-lookup"><span data-stu-id="e7930-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="e7930-141">Необязательное присоединить домен к доменным службам Active Directory (AD DS), включив локальное управление учетными записями безопасности.</span><span class="sxs-lookup"><span data-stu-id="e7930-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="e7930-142">Вы также можете управлять учетной записью локального администратора с помощью Центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="e7930-143">Система комнат Skype обновляется с помощью стандартных процессов Обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e7930-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="e7930-144">Система комнат Skype подключается к Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="e7930-145">Skype для бизнеса использует все виды шифрования и авторизации для всех режимов связи</span><span class="sxs-lookup"><span data-stu-id="e7930-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="e7930-146">Система комнат Skype поддерживает стандарты безопасности и соответствия требованиям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="e7930-147">Дополнительные [сведения см.](../../plan-your-deployment/security/security.md) в сведениях о планировании безопасности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e7930-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="e7930-148">Лицензия</span><span class="sxs-lookup"><span data-stu-id="e7930-148">License</span></span>

<span data-ttu-id="e7930-149">Убедитесь, что для активации программного обеспечения используется KMS.</span><span class="sxs-lookup"><span data-stu-id="e7930-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="e7930-150">В этом случае вам может потребоваться проверить или добавить в него ключ KMS клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="e7930-151">Если вы не используете KMS, запросить ключ корпоративного лицензирования для ключа MAK клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="e7930-152">Ключи лицензий</span><span class="sxs-lookup"><span data-stu-id="e7930-152">License keys</span></span>

<span data-ttu-id="e7930-153">Система комнат Skype запускает настольный клиент Skype для бизнеса в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="e7930-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="e7930-154">Если система комнат Skype является членом домена, она обнаружит ваш KMS.</span><span class="sxs-lookup"><span data-stu-id="e7930-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="e7930-155">(и если он имеет ключ KMS корпоративного лицензирования, он будет активироваться автоматически).</span><span class="sxs-lookup"><span data-stu-id="e7930-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="e7930-156">Корпоративное лицензирование также предоставляет mak, который вы вводите при отобраобраи xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="e7930-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="e7930-157">(Для активации с помощью MAK необходим доступ к Интернету, но не KMS).</span><span class="sxs-lookup"><span data-stu-id="e7930-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="e7930-158">Дополнительные сведения см. в теме "Активация office 2013 с многояговиной активацией".</span><span class="sxs-lookup"><span data-stu-id="e7930-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="e7930-159">Чтобы ввести ключ MAK, перейдите в средство лицензирования SRS "Параметры \> OEM".</span><span class="sxs-lookup"><span data-stu-id="e7930-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="e7930-160">Щелкните Проверить состояние .</span><span class="sxs-lookup"><span data-stu-id="e7930-160">Click Check Status.</span></span> <span data-ttu-id="e7930-161">Если в состоянии "продукт не активирован", введите ключ.</span><span class="sxs-lookup"><span data-stu-id="e7930-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="e7930-162">Если во время активации вы получите сообщение об ошибке "'Служба лицензирования программного обеспечения сообщила, что ключ продукта недействителен", убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="e7930-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="e7930-163">Ключ введен правильно.</span><span class="sxs-lookup"><span data-stu-id="e7930-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="e7930-164">Вы ввели ключ MAK Skype для бизнеса, а не другой ключ.</span><span class="sxs-lookup"><span data-stu-id="e7930-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="e7930-165">Система имеет доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e7930-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="e7930-166">Вы можете активироваться по телефону, но сначала должны были попытаться активироваться с помощью средства лицензирования SRS.</span><span class="sxs-lookup"><span data-stu-id="e7930-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="e7930-167">Чтобы активироваться по телефону, начните тестовую встречу (а не тестовый звонок, так как он слишком короткий).</span><span class="sxs-lookup"><span data-stu-id="e7930-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="e7930-168">В мастере активации Office выберите "Активация по телефону", позвоните в корпорацию Майкрософт, введите длинный номер и введите ответ.</span><span class="sxs-lookup"><span data-stu-id="e7930-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="e7930-169">Certificate Authority</span><span class="sxs-lookup"><span data-stu-id="e7930-169">Certificate Authority</span></span>

<span data-ttu-id="e7930-170">Подтвердим, что в сертификате Office Web Apps Server 2013, используемом для выдачи сертификата Office Web Apps Server 2013, есть HTTP-путь, включенный в свойство списка отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e7930-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="e7930-171">Импорт файла сертификата (CRT) в систему комнат Skype при использовании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e7930-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="e7930-172">Его легко получить из папки CertEnroll сервера ЦС или в папке "Доверенный корневой" любого компьютера, который присоединяется к домену.</span><span class="sxs-lookup"><span data-stu-id="e7930-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="e7930-173">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="e7930-173">Certificates</span></span>

<span data-ttu-id="e7930-174">Убедитесь, что в вашем сертификате есть http-путь для списка отзыва сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e7930-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="e7930-175">Если нет, обновите свой ЦС, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="e7930-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="e7930-176">Установите сертификаты в конфигурации администратора системы комнат Skype в диспетчере сертификатов \> параметров системы.</span><span class="sxs-lookup"><span data-stu-id="e7930-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="e7930-177">Для внутреннего сертификата необходим корпоративный корневой ЦС.</span><span class="sxs-lookup"><span data-stu-id="e7930-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="e7930-178">Один из способов получить необходимые сертификаты — обнаружить ЦС, выдав сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e7930-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="e7930-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span><span class="sxs-lookup"><span data-stu-id="e7930-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="e7930-180">Откроется веб-страница, защищенная ЦС, выдав внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e7930-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="e7930-181">Щелкните значок "Блокировка" в адресной панели браузера, чтобы отобразить отчет о безопасности.</span><span class="sxs-lookup"><span data-stu-id="e7930-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="e7930-182">Щелкните "Просмотреть сертификаты" и проверьте свойство точки распространения CRL.</span><span class="sxs-lookup"><span data-stu-id="e7930-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="e7930-183">Второй параметр CN должен быть именем сервера ЦС.</span><span class="sxs-lookup"><span data-stu-id="e7930-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="e7930-184">Теперь откройте проводник Windows для этого \\ \< CA Server Name \> адреса \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="e7930-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="e7930-185">Скопируйте два CRL-файла и CRT-файл на флэш-накопитель и поместите его в левую часть СМАРТ-доски.</span><span class="sxs-lookup"><span data-stu-id="e7930-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="e7930-186">Импортировать CRT-файл в систему комнат Skype в папке "Доверенный центр сертификации помещений".</span><span class="sxs-lookup"><span data-stu-id="e7930-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="e7930-187">Импортировать CRL-файлы в систему комнат Skype в папку промежуточных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e7930-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="e7930-188">(Чтобы увидеть файлы, необходимо изменить фильтр расширения файлов в диспетчере сертификатов на CRL).</span><span class="sxs-lookup"><span data-stu-id="e7930-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="e7930-189">Примечание. Сервер Office Web Apps 2013 может совместно использовать тот же ЦС, что и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7930-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="e7930-190">Если это не так, вы не сможете поделиться PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="e7930-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="e7930-191">Ознакомьтесь с ИТ-ит-частью и получите CRT- и CRL-файлы из сетевой папки ЦС CertEnroll, как поясняется выше.</span><span class="sxs-lookup"><span data-stu-id="e7930-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="e7930-192">Членство в домене может упростить некоторые аспекты, так как вы можете рассматривать систему комнат Skype как систему Windows и использовать Active Directory для некоторых аспектов сертификата.</span><span class="sxs-lookup"><span data-stu-id="e7930-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="e7930-193">Тем не менее, лучше управлять этим вручную.</span><span class="sxs-lookup"><span data-stu-id="e7930-193">However, it's best to manually manage this.</span></span>
  

