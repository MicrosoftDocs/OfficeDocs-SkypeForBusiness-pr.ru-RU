---
title: Возможности управления и инструменты для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: В этом разделе описываются возможности инструментов управления для Системы комнат Skype.
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293545"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="be53a-103">Возможности управления и инструменты для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="be53a-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="be53a-104">В этом разделе описываются возможности инструментов управления для Системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="be53a-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="be53a-105">Портал администрирования</span><span class="sxs-lookup"><span data-stu-id="be53a-105">Administrative Portal</span></span>

<span data-ttu-id="be53a-106">Для локальных развертываний Skype для бизнеса Server вы можете управлять разрешениями на управление комнатой Skype в Организации с помощью административного портала для помещения в Skype.</span><span class="sxs-lookup"><span data-stu-id="be53a-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="be53a-107">Для получения дополнительных сведений ознакомьтесь со следующей статьей:</span><span class="sxs-lookup"><span data-stu-id="be53a-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="be53a-108">Развертывание веб-портала администрирования SRS v1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="be53a-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="be53a-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="be53a-109">System Center Operations Manager</span></span>

<span data-ttu-id="be53a-110">С помощью System Center Operations Manager (SCOM) можно наблюдать за системой комнаты Skype, загружая [пакет управления комнатой Skype](https://www.microsoft.com/download/details.aspx?id=42320) и устанавливая его на сервер SCOM.</span><span class="sxs-lookup"><span data-stu-id="be53a-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="be53a-111">Вы можете использовать SCOM для настройки оповещений, контроля за работоспособностью системы помещения в Skype, создания отчетов о времени работы и многого другого.</span><span class="sxs-lookup"><span data-stu-id="be53a-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="be53a-112">Система комнат Skype поставляется с предварительно установленным агентом мониторинга, который можно настроить так, чтобы он указывал на сервер SCOM.</span><span class="sxs-lookup"><span data-stu-id="be53a-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="be53a-113">Ознакомьтесь с руководством по установке, предоставленным производителем системы для помещения в Skype, чтобы узнать, как настроить агент мониторинга в системе комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="be53a-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="be53a-114">Контрольный список Exchange</span><span class="sxs-lookup"><span data-stu-id="be53a-114">Exchange Checklist</span></span>

- <span data-ttu-id="be53a-115">Убедитесь, что автообнаружение настроено и внутренняя запись DNS A/CNAME RECORD доступна для домена autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="be53a-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="be53a-116">Проверьте связь автообнаружения (например, проверьте связь с доменом Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="be53a-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="be53a-117">Протестируйте службу автообнаружения с помощью анализатора подключений корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="be53a-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="be53a-118">Выберите первый тест, "я не могу войти в Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="be53a-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="be53a-119">Если в комнате собрания уже есть почтовый ящик ресурсов, расширьте эту учетную запись для системы помещения Skype (пример сценария в нижней части страницы).</span><span class="sxs-lookup"><span data-stu-id="be53a-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="be53a-120">Контрольный список Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="be53a-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="be53a-121">Запустите следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="be53a-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="be53a-122">Анализатор соответствия рекомендациям для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="be53a-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="be53a-123">Средство анализа работоспособности Skype для бизнеса (Excel)</span><span class="sxs-lookup"><span data-stu-id="be53a-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="be53a-124">Анализатор подключений к Skype для бизнеса (32 – бит или 64-разр.)</span><span class="sxs-lookup"><span data-stu-id="be53a-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="be53a-125">Ознакомьтесь [с новыми полезными инструментами для устранения неполадок и анализа для Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="be53a-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="be53a-126">Убедитесь в том, что у вас есть пул Skype для бизнеса и сервер Office Web Apps, и можете поделиться колодой PowerPoint с помощью клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="be53a-127">Если в комнате собрания уже есть почтовый ящик ресурсов, включите его для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="be53a-128">При необходимости запросите DID (номер телефона) для системы комнат переговоров и обновите поле "Общий телефон" в инструменте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be53a-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="be53a-129">Сеть</span><span class="sxs-lookup"><span data-stu-id="be53a-129">Network</span></span>

- <span data-ttu-id="be53a-130">Убедитесь, что у вас есть проводное сетевое подключение для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="be53a-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="be53a-131">Ознакомьтесь с руководством по планированию сети для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="be53a-132">Запросить оценку сети Skype для бизнеса у партнера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="be53a-133">Ознакомьтесь с данными о производительности, сохраненными в средстве анализа работоспособности Skype для бизнеса (Excel).</span><span class="sxs-lookup"><span data-stu-id="be53a-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="be53a-134">Запустите инструмент анализа сети.</span><span class="sxs-lookup"><span data-stu-id="be53a-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="be53a-135">Запустите инструмент PreCall Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="be53a-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="be53a-136">Безопасность системы для помещения в Skype</span><span class="sxs-lookup"><span data-stu-id="be53a-136">Skype Room System Security</span></span>

<span data-ttu-id="be53a-137">Система комнат Skype — это внедренная система, которая может быть полностью интегрирована в развертывание Windows с помощью модели безопасности Skype для бизнеса, управления правами и инструментов управления, например SCOM.</span><span class="sxs-lookup"><span data-stu-id="be53a-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="be53a-138">Доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="be53a-138">Features include:</span></span>
  
- <span data-ttu-id="be53a-139">Фильтр записи для предоставления записи на диск в пользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="be53a-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="be53a-p105">Блокировщик приложений для предотвращения запуска несанкционированных приложений. В пользовательском режиме все порты USB отключены.</span><span class="sxs-lookup"><span data-stu-id="be53a-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="be53a-142">Никакие стандартные приложения и зрители не находились на оборудовании системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="be53a-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="be53a-143">All content is rendered via HTTP or RDP protocols.</span><span class="sxs-lookup"><span data-stu-id="be53a-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="be53a-p107">Бытовой компьютер работает под управлением операционной системы Windows Embedded Standard 7. Все оборудование, включая устройства, предоставляются партнерами изготовителя оборудования.</span><span class="sxs-lookup"><span data-stu-id="be53a-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="be53a-146">Присоединение необязательного домена к службе Active Directory Domain Services (AD DS) обеспечивает управление и контроль локальных учетных записей безопасности.</span><span class="sxs-lookup"><span data-stu-id="be53a-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="be53a-147">Вы также можете управлять учетной записью локального администратора с помощью центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="be53a-148">Система комнат Skype обновляется с помощью стандартных процессов центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="be53a-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="be53a-149">Система комнат Skype подключается к Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="be53a-150">Skype для бизнеса использует полное шифрование и авторизацию для всех режимов общения.</span><span class="sxs-lookup"><span data-stu-id="be53a-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="be53a-151">Система комнат Skype поддерживает стандарты безопасности и соответствия требованиям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="be53a-152">Дополнительные сведения приведены [в разделе Планирование безопасности в Skype для бизнеса Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="be53a-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="be53a-153">Лицензия</span><span class="sxs-lookup"><span data-stu-id="be53a-153">License</span></span>

<span data-ttu-id="be53a-154">Убедитесь, что используете KMS для активации программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="be53a-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="be53a-155">Если да, возможно, потребуется проверить или добавить в него ключ KMS для клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="be53a-156">Если вы не используете службу KMS, запросите ключ корпоративного лицензирования для ключа MAK клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="be53a-157">Ключи лицензии</span><span class="sxs-lookup"><span data-stu-id="be53a-157">License keys</span></span>

<span data-ttu-id="be53a-158">Система помещения Skype для настольного компьютера запускает Настольный клиент Skype для бизнеса в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="be53a-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="be53a-159">Если система комнаты Skype входит в состав домена, она обнаружит ваш сервер управления ключами.</span><span class="sxs-lookup"><span data-stu-id="be53a-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="be53a-160">(и если у него есть ключ KMS для корпоративного лицензирования, он будет активирован автоматически).</span><span class="sxs-lookup"><span data-stu-id="be53a-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="be53a-161">Корпоративное лицензирование также предоставляет ключ MAK, который вводится в формате XXXXX-XXXXX-XXXXX-XXXXX.</span><span class="sxs-lookup"><span data-stu-id="be53a-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="be53a-162">(Доступ к Интернету требуется для активации с использованием ключа MAK, но не для KMS).</span><span class="sxs-lookup"><span data-stu-id="be53a-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="be53a-163">Дополнительные сведения можно найти в разделе многопользовательская активация Office 2013.</span><span class="sxs-lookup"><span data-stu-id="be53a-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="be53a-164">Для ввода ключа MAK перейдите к средству лицензирования SRS \> для OEM-параметров.</span><span class="sxs-lookup"><span data-stu-id="be53a-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="be53a-165">Выберите "Проверка состояния".</span><span class="sxs-lookup"><span data-stu-id="be53a-165">Click Check Status.</span></span> <span data-ttu-id="be53a-166">Когда отображается сообщение о том, что продукт не активирован, введите ключ.</span><span class="sxs-lookup"><span data-stu-id="be53a-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="be53a-167">Если во время активации появляется сообщение об ошибке "" Служба лицензирования программного обеспечения сообщила, что этот ключ продукта недействителен ", убедитесь в том, что:</span><span class="sxs-lookup"><span data-stu-id="be53a-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="be53a-168">Ключ введен правильно.</span><span class="sxs-lookup"><span data-stu-id="be53a-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="be53a-169">Вы ввели ключ MAK Skype для бизнеса, а не другой ключ.</span><span class="sxs-lookup"><span data-stu-id="be53a-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="be53a-170">У системы есть доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="be53a-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="be53a-171">Вы можете выполнить активацию с помощью телефона, но сначала потребуется выполнить попытку активации с помощью средства лицензирования SRS.</span><span class="sxs-lookup"><span data-stu-id="be53a-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="be53a-172">Для активации через телефон начните тестовое собрание (не тестовый звонок, так как он слишком короткий).</span><span class="sxs-lookup"><span data-stu-id="be53a-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="be53a-173">В мастере активации Office выберите Активация по телефону, звоните в корпорацию Майкрософт, введите длинный номер и введите ответ.</span><span class="sxs-lookup"><span data-stu-id="be53a-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="be53a-174">Центр сертификации</span><span class="sxs-lookup"><span data-stu-id="be53a-174">Certificate Authority</span></span>

<span data-ttu-id="be53a-175">Убедитесь, что центр сертификации, выдавший сертификат Office Web Apps Server 2013, включил путь HTTP в свойство списка отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="be53a-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="be53a-176">Импорт файла сертификата (CRT) в систему комнаты Skype при использовании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be53a-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="be53a-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span><span class="sxs-lookup"><span data-stu-id="be53a-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="be53a-178">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="be53a-178">Certificates</span></span>

<span data-ttu-id="be53a-p114">Убедитесь, что у Центра сертификации есть путь http для списка отзыва сертификатов (CRL). Если нет, обновите Центр сертификации, чтобы добавить путь.</span><span class="sxs-lookup"><span data-stu-id="be53a-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="be53a-181">Установите сертификаты в настройках администратора системы комнат Skype в диспетчере сертификатов параметры \> системы.</span><span class="sxs-lookup"><span data-stu-id="be53a-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="be53a-182">You need the Enterprise Root CA for your internal certificate.</span><span class="sxs-lookup"><span data-stu-id="be53a-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="be53a-183">Единственный способ получить необходимые сертификаты — обнаружить центр сертификации, выдавший сертификаты.</span><span class="sxs-lookup"><span data-stu-id="be53a-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="be53a-184">В Skype для бизнеса Server на компьютере с Windows в Skype для бизнеса выберите параметры \> инструменты \> параметры конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="be53a-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="be53a-185">Откроется веб-страница, защищенная центром сертификации, который выдал внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="be53a-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="be53a-186">Нажмите на значок замка в адресной строке браузера для отображения отчета по безопасности.</span><span class="sxs-lookup"><span data-stu-id="be53a-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="be53a-187">Нажмите "Просмотр сертификатов" и проверьте свойство "Точка распространения списка отзыва сертификатов".</span><span class="sxs-lookup"><span data-stu-id="be53a-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="be53a-188">Второй параметр CN должен быть именем сервера центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="be53a-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="be53a-189">Теперь откройте проводник для этого имени \\ \< \>сервера ЦС для этого адреса \цертенролл.</span><span class="sxs-lookup"><span data-stu-id="be53a-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="be53a-190">Скопируйте два файла .crl и файл .crt на устройство флэш-памяти и поместите его с левой части доски SMART.</span><span class="sxs-lookup"><span data-stu-id="be53a-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="be53a-191">Импортируйте файл. CRT в систему помещения Skype в разделе центр сертификации доверенной комнаты.</span><span class="sxs-lookup"><span data-stu-id="be53a-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="be53a-192">Импортируйте файлы. CRL из системы помещения Skype в папке "промежуточные центры сертификации".</span><span class="sxs-lookup"><span data-stu-id="be53a-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="be53a-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span><span class="sxs-lookup"><span data-stu-id="be53a-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="be53a-194">Примечание: Office Web Apps 2013 может использовать тот же центр сертификации, что и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be53a-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="be53a-195">Если вы не можете поделиться PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="be53a-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="be53a-196">Узнайте, как получить доступ к файлам CRT и CRL за пределами сетевого центра сертификации Цертенролл, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="be53a-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="be53a-197">Членство в домене может упростить некоторые действия, так как вы можете рассматривать систему комнат Skype как систему Windows, и для некоторых аспектов сертификата она может полагаться на службу каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be53a-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="be53a-198">However, it's best to manually manage this.</span><span class="sxs-lookup"><span data-stu-id="be53a-198">However, it's best to manually manage this.</span></span>
  

