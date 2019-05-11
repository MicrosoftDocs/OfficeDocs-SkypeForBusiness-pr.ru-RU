---
title: Возможности управления и инструменты для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: В этом разделе описываются возможности инструментов управления для Системы комнат Skype.
ms.openlocfilehash: 8a1d9f3e3d1c569a0473ca92cda6761ce63f0096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895035"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="97f50-103">Возможности управления и инструменты для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="97f50-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="97f50-104">В этом разделе описываются возможности инструментов управления для Системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="97f50-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="97f50-105">Портал администрирования</span><span class="sxs-lookup"><span data-stu-id="97f50-105">Administrative Portal</span></span>

<span data-ttu-id="97f50-106">Для Скайп для локального развертывания Business Server портал администрирования системы комнаты Скайп можно использовать для активно управления и мониторинга системы комнаты Скайп развертываний вашей организации.</span><span class="sxs-lookup"><span data-stu-id="97f50-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="97f50-107">В следующей статье для получения дополнительных сведений:</span><span class="sxs-lookup"><span data-stu-id="97f50-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="97f50-108">Развертывание SRS v1 административного веб-портала в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="97f50-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="97f50-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="97f50-109">System Center Operations Manager</span></span>

<span data-ttu-id="97f50-110">Система Скайп комнаты можно отслеживать через System Center Operations Manager (SCOM), [Пакет управления System комнаты Скайп](https://www.microsoft.com/download/details.aspx?id=42320) загрузив и установив его на сервер SCOM.</span><span class="sxs-lookup"><span data-stu-id="97f50-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="97f50-111">SCOM можно использовать для параметров оповещений, за работоспособностью системы Скайп помещения, создавать отчеты о работоспособности и многое другое.</span><span class="sxs-lookup"><span data-stu-id="97f50-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="97f50-112">Система комнаты Скайп поставляется с предварительно установленные мониторинга агента, который можно настроить для указания на сервер SCOM.</span><span class="sxs-lookup"><span data-stu-id="97f50-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="97f50-113">Обратитесь к руководство по установке предоставлено производителем системы комнаты Скайп необходимо знать о настройке мониторинга агента Скайп комнаты системе.</span><span class="sxs-lookup"><span data-stu-id="97f50-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="97f50-114">Контрольный список Exchange</span><span class="sxs-lookup"><span data-stu-id="97f50-114">Exchange Checklist</span></span>

- <span data-ttu-id="97f50-115">Убедитесь, что автообнаружение настроено и внутренняя запись DNS A/CNAME RECORD доступна для домена autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="97f50-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="97f50-116">Проверьте связь автообнаружения (например, проверьте связь с доменом Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="97f50-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="97f50-117">Протестируйте службу автообнаружения с помощью анализатора подключений корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97f50-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="97f50-118">Выбор первого теста, «Не удается войти с помощью Microsoft Office Outlook.»</span><span class="sxs-lookup"><span data-stu-id="97f50-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="97f50-119">Если зала уже почтового ящика ресурса, расширьте эту учетную запись для системы комнаты Скайп (пример сценария, в нижней части страницы).</span><span class="sxs-lookup"><span data-stu-id="97f50-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="97f50-120">Скайп для бизнеса контрольного списка</span><span class="sxs-lookup"><span data-stu-id="97f50-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="97f50-121">Запустите следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="97f50-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="97f50-122">Скайп для бизнеса анализатора соответствия рекомендациям</span><span class="sxs-lookup"><span data-stu-id="97f50-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="97f50-123">Скайп для средство анализа бизнеса (Excel)</span><span class="sxs-lookup"><span data-stu-id="97f50-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="97f50-124">Скайп для Business Connectivity Analyzer 32-разрядная или 64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="97f50-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="97f50-125">Просмотрите [полезные новые Устранение неполадок и средства анализа для Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="97f50-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="97f50-126">Подтверждение у пользователя имеется Скайп для бизнеса пула и сервера Office Web Apps и могут совместно использовать набор PowerPoint с помощью Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="97f50-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="97f50-127">Если зала уже почтового ящика ресурса, включить эту функцию для Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="97f50-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="97f50-128">При необходимости запросите DID (номер телефона) для системы комнат переговоров и обновите поле "Общий телефон" в инструменте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="97f50-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="97f50-129">Сеть</span><span class="sxs-lookup"><span data-stu-id="97f50-129">Network</span></span>

- <span data-ttu-id="97f50-130">Убедитесь, что у вас есть проводной сети для системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="97f50-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="97f50-131">Чтение сети, руководство по планированию для Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="97f50-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="97f50-132">Запросите Скайп для оценки бизнеса сети Скайп для делового партнера.</span><span class="sxs-lookup"><span data-stu-id="97f50-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="97f50-133">Внимательно прочесть данные о производительности получил в Скайп средство анализа бизнеса (Excel).</span><span class="sxs-lookup"><span data-stu-id="97f50-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="97f50-134">Запустите инструмент анализа сети.</span><span class="sxs-lookup"><span data-stu-id="97f50-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="97f50-135">Запустите инструмент PreCall Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="97f50-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="97f50-136">Скайп места системы безопасности</span><span class="sxs-lookup"><span data-stu-id="97f50-136">Skype Room System Security</span></span>

<span data-ttu-id="97f50-137">Скайп помещения – внедренных система, полностью интегрирован в развертывании Windows, с помощью Скайп для бизнес-модели безопасности, управления правами и средства управления, такие как SCOM.</span><span class="sxs-lookup"><span data-stu-id="97f50-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="97f50-138">Доступны следующие функции.</span><span class="sxs-lookup"><span data-stu-id="97f50-138">Features include:</span></span>
  
- <span data-ttu-id="97f50-139">Фильтр записи для предоставления записи на диск в пользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="97f50-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="97f50-p105">Блокировщик приложений для предотвращения запуска несанкционированных приложений. В пользовательском режиме все порты USB отключены.</span><span class="sxs-lookup"><span data-stu-id="97f50-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="97f50-142">Нет стандартных приложений или средства просмотра хранятся на устройстве Скайп комнаты оборудовании.</span><span class="sxs-lookup"><span data-stu-id="97f50-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="97f50-143">All content is rendered via HTTP or RDP protocols.</span><span class="sxs-lookup"><span data-stu-id="97f50-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="97f50-p107">Бытовой компьютер работает под управлением операционной системы Windows Embedded Standard 7. Все оборудование, включая устройства, предоставляются партнерами изготовителя оборудования.</span><span class="sxs-lookup"><span data-stu-id="97f50-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="97f50-146">Присоединение необязательного домена к службе Active Directory Domain Services (AD DS) обеспечивает управление и контроль локальных учетных записей безопасности.</span><span class="sxs-lookup"><span data-stu-id="97f50-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="97f50-147">Также можно управлять с помощью Скайп по центру администрирования Business учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="97f50-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="97f50-148">Система комнаты Скайп обновляется посредством стандартных процессов Центр обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="97f50-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="97f50-149">Система комнаты Скайп подключается с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="97f50-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="97f50-150">Скайп для бизнеса с помощью шифрования начала до конца и авторизации для всех режимы связи</span><span class="sxs-lookup"><span data-stu-id="97f50-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="97f50-151">Система комнаты Скайп поддерживает Скайп для бизнеса безопасность и соответствие требованиям стандартов.</span><span class="sxs-lookup"><span data-stu-id="97f50-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="97f50-152">[Безопасность в Скайп Business Server](../../plan-your-deployment/security/security.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="97f50-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="97f50-153">Лицензия</span><span class="sxs-lookup"><span data-stu-id="97f50-153">License</span></span>

<span data-ttu-id="97f50-154">Убедитесь, что используете KMS для активации программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="97f50-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="97f50-155">Если это так, может потребоваться проверить или добавить Скайп для бизнеса клиентский ключ KMS.</span><span class="sxs-lookup"><span data-stu-id="97f50-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="97f50-156">Если вы не используете KMS, запросите ключа корпоративной лицензии для Скайп для клиента Business MAK.</span><span class="sxs-lookup"><span data-stu-id="97f50-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="97f50-157">Ключи лицензии</span><span class="sxs-lookup"><span data-stu-id="97f50-157">License keys</span></span>

<span data-ttu-id="97f50-158">Система комнаты Скайп запускает Скайп для настольных компьютеров клиента Business в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="97f50-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="97f50-159">Если система комнаты Скайп является членом домена, ему будет обнаружить вашей KMS.</span><span class="sxs-lookup"><span data-stu-id="97f50-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="97f50-160">(и, если он имеет Volume Licensing ключ KMS автоматическая активация).</span><span class="sxs-lookup"><span data-stu-id="97f50-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="97f50-161">Volume Licensing также предоставляет ключ MAK, который вводится как отображает xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="97f50-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="97f50-162">(Требуется доступ к Интернету для активации с помощью ключа MAK, но не KMS).</span><span class="sxs-lookup"><span data-stu-id="97f50-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="97f50-163">Дополнительные сведения см в многопользовательской активации Office 2013.</span><span class="sxs-lookup"><span data-stu-id="97f50-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="97f50-164">Чтобы ввести ключ многократной Активации, перейдите в раздел ПВТ параметры \> средство лицензирования SRS.</span><span class="sxs-lookup"><span data-stu-id="97f50-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="97f50-165">Выберите "Проверка состояния".</span><span class="sxs-lookup"><span data-stu-id="97f50-165">Click Check Status.</span></span> <span data-ttu-id="97f50-166">Когда состояние с текстом «продукт не активирован», введите ключ.</span><span class="sxs-lookup"><span data-stu-id="97f50-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="97f50-167">Если во время активации появится сообщение о том, «"Служба лицензирования программного обеспечения сообщает, что ключ продукта недействителен,» затем убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="97f50-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="97f50-168">Ключ введен правильно.</span><span class="sxs-lookup"><span data-stu-id="97f50-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="97f50-169">Скайп ввести ключ многократной Активации бизнеса и не другой ключ.</span><span class="sxs-lookup"><span data-stu-id="97f50-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="97f50-170">У системы есть доступ к Интернету.</span><span class="sxs-lookup"><span data-stu-id="97f50-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="97f50-171">Вы можете выполнить активацию с помощью телефона, но сначала потребуется выполнить попытку активации с помощью средства лицензирования SRS.</span><span class="sxs-lookup"><span data-stu-id="97f50-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="97f50-172">Для активации через телефон начните тестовое собрание (не тестовый звонок, так как он слишком короткий).</span><span class="sxs-lookup"><span data-stu-id="97f50-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="97f50-173">В окне мастера активации Office выберите активация по телефону, звонок Microsoft, ввести длинный номер и введите ответ.</span><span class="sxs-lookup"><span data-stu-id="97f50-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="97f50-174">Центр сертификации</span><span class="sxs-lookup"><span data-stu-id="97f50-174">Certificate Authority</span></span>

<span data-ttu-id="97f50-175">Убедитесь, что центр сертификации, выдавший сертификат Office Web Apps Server 2013, включил путь HTTP в свойство списка отзыва сертификатов (CRL).</span><span class="sxs-lookup"><span data-stu-id="97f50-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="97f50-176">Импортируйте файл сертификата (.crt) системы комнаты Скайп при использовании Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="97f50-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="97f50-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span><span class="sxs-lookup"><span data-stu-id="97f50-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="97f50-178">Сертификаты</span><span class="sxs-lookup"><span data-stu-id="97f50-178">Certificates</span></span>

<span data-ttu-id="97f50-p114">Убедитесь, что у Центра сертификации есть путь http для списка отзыва сертификатов (CRL). Если нет, обновите Центр сертификации, чтобы добавить путь.</span><span class="sxs-lookup"><span data-stu-id="97f50-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="97f50-181">Установка сертификатов в программе установки администрирования системы Скайп помещений в разделе Параметры системы \> диспетчера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="97f50-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="97f50-182">You need the Enterprise Root CA for your internal certificate.</span><span class="sxs-lookup"><span data-stu-id="97f50-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="97f50-183">Единственный способ получить необходимые сертификаты — обнаружить центр сертификации, выдавший сертификаты.</span><span class="sxs-lookup"><span data-stu-id="97f50-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="97f50-184">Для Скайп сервера Business на ПК в Скайп для бизнеса, нажмите кнопку Параметры \> средств \> параметры конференции.</span><span class="sxs-lookup"><span data-stu-id="97f50-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="97f50-185">Откроется веб-страница с центром сертификации, выпустивший внутренние сертификаты.</span><span class="sxs-lookup"><span data-stu-id="97f50-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="97f50-186">Нажмите на значок замка в адресной строке браузера для отображения отчета по безопасности.</span><span class="sxs-lookup"><span data-stu-id="97f50-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="97f50-187">Нажмите "Просмотр сертификатов" и проверьте свойство "Точка распространения списка отзыва сертификатов".</span><span class="sxs-lookup"><span data-stu-id="97f50-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="97f50-188">Второй параметр CN должен быть именем сервера центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="97f50-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="97f50-189">Теперь откройте проводник Windows для этого адреса \\ \< имя сервера центра сертификации \>\CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="97f50-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="97f50-190">Скопируйте два файла .crl и файл .crt на устройство флэш-памяти и поместите его с левой части доски SMART.</span><span class="sxs-lookup"><span data-stu-id="97f50-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="97f50-191">Импортируйте файл .crt системы комнаты Скайп в папке доверенного центра сертификации комнаты.</span><span class="sxs-lookup"><span data-stu-id="97f50-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="97f50-192">Импорт файлов .crl в системе комнаты Скайп в папке промежуточные центры сертификации.</span><span class="sxs-lookup"><span data-stu-id="97f50-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="97f50-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span><span class="sxs-lookup"><span data-stu-id="97f50-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="97f50-194">Примечание: Сервер Office Web Apps 2013 могут совместно использовать же сертификации как Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="97f50-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="97f50-195">Если это не так вы не сможете совместное использование PowerPoint на собрании.</span><span class="sxs-lookup"><span data-stu-id="97f50-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="97f50-196">Обратитесь к ИТ и получить CRT и файлы CRL подключен к сети ЦС совместно использовать CertEnroll, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="97f50-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="97f50-197">Членство в домене позволяет упростить некоторые факторы, поскольку системы Скайп комнаты можно рассматривать как системы Windows и его можно использовать Active Directory для некоторых аспектов сертификата.</span><span class="sxs-lookup"><span data-stu-id="97f50-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="97f50-198">However, it's best to manually manage this.</span><span class="sxs-lookup"><span data-stu-id="97f50-198">However, it's best to manually manage this.</span></span>
  

