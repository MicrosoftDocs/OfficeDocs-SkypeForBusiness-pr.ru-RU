---
title: 'Lync Server 2013: Настройка Федерации XMPP'
description: 'Lync Server 2013: Настройка Федерации XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555705"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="fba09-103">Настройка Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba09-103">Setting up XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba09-104">_**Последнее изменение темы:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="fba09-104">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="fba09-p101">Для развертывания прокси-сервера XMPP на пограничном сервере необходимо настроить пограничный сервер для федерации XMPP. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fba09-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="fba09-107">Настройка федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="fba09-107">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="fba09-108">Выполните вход на компьютер, на котором установлен мастер развертывания Lync Server, в качестве члена группы администраторов домена и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fba09-108">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="fba09-p102">На сервере переднего плана откройте мастер развертывания Lync Server. Последовательно выберите пункты "Install or Update Lync Server System" ("Установка или обновление системы Lync Server") и "Setup or Remove Lync Server Components" ("Установка или удаление компонентов Lync Server"). Нажмите "Run Again" ("Запустить снова").</span><span class="sxs-lookup"><span data-stu-id="fba09-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="fba09-p103">В окне установки компонентов Lync Server нажмите кнопку "Далее". В экране сводки будут показываться действия по мере их выполнения. После выполнения развертывания нажмите "Просмотр журнала", чтобы просмотреть доступные файлы журналов. Чтобы завершить развертывание, нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="fba09-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="fba09-p104">На пограничном сервере откройте мастер развертывания Lync Server. Последовательно выберите пункты "Install or Update Lync Server System" ("Установка или обновление системы Lync Server") и "Setup or Remove Lync Server Components" ("Установка или удаление компонентов Lync Server"). Нажмите "Run Again" ("Запустить снова").</span><span class="sxs-lookup"><span data-stu-id="fba09-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="fba09-p105">В окне установки компонентов Lync Server нажмите кнопку "Далее". В экране сводки будут показываться действия по мере их выполнения. После выполнения развертывания нажмите "Просмотр журнала", чтобы просмотреть доступные файлы журналов. Чтобы завершить развертывание, нажмите кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="fba09-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="fba09-123">На пограничном сервере в мастере развертывания рядом с пунктом "Step 3: Request, Install, or Assign Certificates" ("Шаг 3. Запрос, установка или назначение сертификатов") нажмите "Run again" ("Запустить снова").</span><span class="sxs-lookup"><span data-stu-id="fba09-123">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="fba09-124">Если развертывание пограничного сервера выполняется впервые, то вместо кнопки "Run Again" ("Запустить снова") появится кнопка "Run" ("Запустить").</span><span class="sxs-lookup"><span data-stu-id="fba09-124">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="fba09-125">На странице "Available Certificate Tasks" ("Доступные задачи с сертификатами") выберите "Create a new certificate request" ("Создать новый запрос сертификата").</span><span class="sxs-lookup"><span data-stu-id="fba09-125">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="fba09-126">На странице запрос сертификата щелкните сертификат внешнего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="fba09-126">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="fba09-127">На странице "Delayed or Immediate Request" ("Отложенный или немедленный запрос") установите флажок "Prepare the request now, but send it later" ("Подготовить запрос сейчас, чтобы отправить его позже").</span><span class="sxs-lookup"><span data-stu-id="fba09-127">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="fba09-128">На странице файл запроса сертификата введите полный путь и имя файла, в который будет сохранен запрос (например, c: \\ CERT \_ ексернал \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="fba09-128">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="fba09-129">На странице "Specify Alternate Certificate Template" ("Указать другой шаблон сертификата")  установите флажок "Use alternative certificate template for the selected certification authority" ("Использовать другой шаблон для выбранного центра сертификации"), чтобы использовать шаблон сертификата, отличный от установленного по умолчанию шаблона WebServer.</span><span class="sxs-lookup"><span data-stu-id="fba09-129">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="fba09-130">На странице "Name and Security Settings" ("Имя и параметры безопасности") выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fba09-130">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="fba09-131">В поле "Friendly name" ("Понятное имя") введите отображаемое имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="fba09-131">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="fba09-132">В поле "Bit length" ("Длина в битах")  задайте длину в битах (обычно это установленное по умолчанию значение 2048).</span><span class="sxs-lookup"><span data-stu-id="fba09-132">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="fba09-133">Убедитесь, что установлен флажок "Mark certificate private key as exportable" ("Пометить закрытый ключ сертификата как экспортируемый").</span><span class="sxs-lookup"><span data-stu-id="fba09-133">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="fba09-134">На странице "Organization Information" ("Сведения об организации") введите имя организации и подразделение (например, отделение или отдел).</span><span class="sxs-lookup"><span data-stu-id="fba09-134">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="fba09-135">На странице "Geographical Information" ("Сведения о местоположении") укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="fba09-135">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="fba09-p106">На странице "Subject Name/Subject Alternate Names" ("Имя субъекта/альтернативные имена субъектов") отображаются сведения, автоматически заполненные мастером. Если нужны дополнительные альтернативные имена субъектов, укажите их в следующих двух действиях.</span><span class="sxs-lookup"><span data-stu-id="fba09-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="fba09-138">На странице Параметры домена SIP в альтернативных именах субъектов (SAN) установите флажок домен, чтобы добавить SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="fba09-138">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="fba09-139">запись в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="fba09-139">entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="fba09-140">На странице "Configure Additional Subject Alternate Names" ("Настройка дополнительных альтернативных имен субъекта") укажите все нужные дополнительные альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="fba09-140">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="fba09-p108">Если устанавливается прокси-сервер XMPP, то по умолчанию в записях SAN появляется имя домена (например, contoso.com). Если нужны дополнительные записи, добавьте их на этом шаге.</span><span class="sxs-lookup"><span data-stu-id="fba09-p108">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="fba09-143">На странице "Request Summary" ("Сводка по запросу") просмотрите сведения о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="fba09-143">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="fba09-144">После завершения выполнения команд можно просмотреть журналы или для продолжения нажать кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="fba09-144">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="fba09-145">На странице "Certificate Request File" ("Файл запроса сертификата") можно просмотреть файл запроса подписи сертификата (CSR-файл), нажав кнопку "View" ("Просмотр"), или выйти из мастера сертификатов, нажав кнопку "Готово".</span><span class="sxs-lookup"><span data-stu-id="fba09-145">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="fba09-146">Скопируйте этот файл запроса и отправьте его в свой общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="fba09-146">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="fba09-p109">После получения, импорта и назначения общедоступного сертификата необходимо остановить и перезапустить службы пограничного сервера. Это можно сделать, введя в консоли управления Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fba09-p109">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="fba09-149">Чтобы настроить DNS для Федерации XMPP, добавьте следующую запись SRV к внешнему DNS: \_ XMPP-Server. \_ семейства.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="fba09-149">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="fba09-150">Запись SRV будет разрешаться в полное доменное имя пограничного сервера доступа, при этом значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="fba09-150">The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="fba09-151">Кроме того, вы настраиваете запись узла "A" (например, xmpp.contoso.com), которая указывает на IP-адрес пограничного сервера доступа.</span><span class="sxs-lookup"><span data-stu-id="fba09-151">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fba09-p111">При наличии пограничных пулов в нескольких сайтах рекомендуется добавить несколько SRV-записей для федерации XMPP. Добавьте SRV-запись для каждого пограничного пула в организации и предоставьте каждой SRV-записи собственный приоритет. При работе всех пулов пограничных серверов запросы XMPP будут обрабатываться пограничным пулом с первым приоритетом, однако если этот пограничный пул станет неработоспособным,  не нужно будет добавлять новую SRV-запись для восстановления функций федерации XMPP.</span><span class="sxs-lookup"><span data-stu-id="fba09-p111">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="fba09-155">Настройте новую политику внешнего доступа, чтобы включить всех пользователей, открыв командную консоль Lync Server на сервере переднего плана и введя в ней следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fba09-155">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="fba09-156">Включите XMPP-доступ для внешних пользователей, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fba09-156">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="fba09-157">На пограничном сервере, на котором развернут прокси-сервер XMPP, откройте командную строку или интерфейс командной строки Windows PowerShell™ и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fba09-157">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="fba09-158">Команда **netstat – АНО** — это команда сетевой статистики, запрос Parameters **— АНО** , который отображает все подключения и порты, адреса и порты отображаются в виде числовых форм и с каждым подключением связан идентификатор процесса-владельца.</span><span class="sxs-lookup"><span data-stu-id="fba09-158">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="fba09-159">Символ **|** определяет канал для следующей команды, **findstr**или String Find.</span><span class="sxs-lookup"><span data-stu-id="fba09-159">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="fba09-160">Число 5269 и 23456, которое передается в findstr в качестве параметра, дает команду findstr для поиска в выходных данных netstat для строк 5269 и 23456.</span><span class="sxs-lookup"><span data-stu-id="fba09-160">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="fba09-161">Если XMPP настроен правильно, результат выполнения команд должен привести к прослушиванию и установлению подключений как на внешнем интерфейсе (порт 5269), так и во внутреннем интерфейсе (Port 23456) пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="fba09-161">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="fba09-162">Если команды не возвращают сведения об установленных подключениях или прослушивании по портам 5269 и 23456, проверьте приведенные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="fba09-162">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="fba09-163">Устранение неполадок, связанных с федерацией XMPP</span><span class="sxs-lookup"><span data-stu-id="fba09-163">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="fba09-164">Чтобы определить, работает ли прокси-сервер XMPP, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fba09-164">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="fba09-165">Выполните вход на пограничный сервер, на котором работает служба прокси-сервера XMPP, от имени члена группы локальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="fba09-165">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="fba09-166">Щелкните **Пуск**, **Все программы**, **Средства администрирования**, затем **Службы**</span><span class="sxs-lookup"><span data-stu-id="fba09-166">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="fba09-p113">В оснастке "Службы" найдите службу "Прокси-сервер шлюза преобразования XMPP Lync Server". Эта служба должна быть в состоянии **Работает**. Если она не запущена, щелкните значок **Запуск службы** на панели инструментов. Значок принимает вид зеленой стрелки, направленной вправо.</span><span class="sxs-lookup"><span data-stu-id="fba09-p113">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="fba09-p114">Убедитесь, что состояние службы указано как **Работает**. Если служба запустилась успешно, закройте оснастку **Службы** и продолжите работу.</span><span class="sxs-lookup"><span data-stu-id="fba09-p114">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="fba09-173">Если служба не запустилась успешно, в средствах администрирования откройте средство просмотра событий и просмотрите ошибки и предупреждения в разделе **Lync Server\*\*\*\*журналов приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="fba09-173">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="fba09-174">После запуска службы **Шлюз преобразования XMPP Lync Server** повторно выполните вышеуказанные команды netstat.</span><span class="sxs-lookup"><span data-stu-id="fba09-174">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="fba09-175">Если вы не видите установленные или прослушиваемые сеансы, проверьте и убедитесь, что в построителе топологий правильно настроен **маршрут Федерации XMPP**</span><span class="sxs-lookup"><span data-stu-id="fba09-175">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="fba09-176">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fba09-176">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="fba09-177">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fba09-177">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="fba09-178">В построителе топологий выберите сайт для маршрута Федерации XMPP и просмотрите его, чтобы убедиться, что **назначение маршрутизации Федерации сайтов** для **Федерации XMPP** показывает пограничный сервер или пограничный пул в качестве выбранного назначения маршрута Федерации XMPP.</span><span class="sxs-lookup"><span data-stu-id="fba09-178">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="fba09-179">Если назначение маршрута неправильно или не задано, щелкните его правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fba09-179">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="fba09-180">Установите флажок Федерация XMPP, а затем выберите правильный пограничный сервер или пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="fba09-180">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="fba09-181">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="fba09-181">Publish the topology.</span></span> <span data-ttu-id="fba09-182">Дополнительные сведения см [в статье публикация топологии в Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fba09-182">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="fba09-183">Хотя это не обязательно и не требуется, может потребоваться перезапустить пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="fba09-183">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="fba09-184">С помощью процесса netstat, который использовался ранее, убедитесь, что пограничный сервер прослушивает или установил сеансы на порте 5269 и порт 23456.</span><span class="sxs-lookup"><span data-stu-id="fba09-184">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="fba09-185">Если ожидаемых сеансов все еще не отображается, просмотрите средство просмотра событий на предмет возможных причин проблем со связью.</span><span class="sxs-lookup"><span data-stu-id="fba09-185">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fba09-186">См. также</span><span class="sxs-lookup"><span data-stu-id="fba09-186">See Also</span></span>


[<span data-ttu-id="fba09-187">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</span><span class="sxs-lookup"><span data-stu-id="fba09-187">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="fba09-188">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba09-188">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

