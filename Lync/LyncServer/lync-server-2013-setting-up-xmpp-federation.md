---
title: 'Lync Server 2013: настройка федерации XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="027ae-102">Настройка федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="027ae-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="027ae-103">_**Тема последнего изменения:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="027ae-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="027ae-104">Для развертывания прокси-сервера КСМПП на пограничном сервере необходимо настроить граничный сервер для КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="027ae-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="027ae-105">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="027ae-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="027ae-106">Настройка Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="027ae-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="027ae-107">Войдите в систему на компьютере, на котором установлен мастер развертывания Lync Server, в группе Администраторы домена и в группу Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="027ae-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="027ae-108">На сервере переднего плана откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="027ae-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="027ae-109">Щелкните Установка или обновление операционной системы Lync Server, а затем нажмите кнопку Настройка или удалите компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="027ae-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="027ae-110">Нажмите кнопку выполнить еще раз.</span><span class="sxs-lookup"><span data-stu-id="027ae-110">Click Run Again.</span></span>

3.  <span data-ttu-id="027ae-111">В разделе Настройка серверных компонентов Lync нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="027ae-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="027ae-112">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="027ae-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="027ae-113">После завершения развертывания щелкните Просмотреть журнал, чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="027ae-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="027ae-114">Нажмите кнопку Готово, чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="027ae-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="027ae-115">На пограничном сервере откройте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="027ae-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="027ae-116">Щелкните Установка или обновление операционной системы Lync Server, а затем нажмите кнопку Настройка или удалите компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="027ae-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="027ae-117">Нажмите кнопку выполнить еще раз.</span><span class="sxs-lookup"><span data-stu-id="027ae-117">Click Run Again.</span></span>

5.  <span data-ttu-id="027ae-118">В разделе Настройка серверных компонентов Lync нажмите кнопку Далее.</span><span class="sxs-lookup"><span data-stu-id="027ae-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="027ae-119">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="027ae-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="027ae-120">После завершения развертывания щелкните Просмотреть журнал, чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="027ae-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="027ae-121">Нажмите кнопку Готово, чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="027ae-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="027ae-122">На пограничном сервере в мастере развертывания рядом с шагом 3: запрос, установка и назначение сертификатов нажмите кнопку выполнить еще раз.</span><span class="sxs-lookup"><span data-stu-id="027ae-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="027ae-123">Если пограничный сервер развертывается в первый раз, вместо повторного запуска вы увидите "запустить".</span><span class="sxs-lookup"><span data-stu-id="027ae-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="027ae-124">На странице Доступные задачи сертификатов щелкните команду Создать новый запрос сертификата.</span><span class="sxs-lookup"><span data-stu-id="027ae-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="027ae-125">На странице запроса сертификата выберите внешний Граничный сертификат.</span><span class="sxs-lookup"><span data-stu-id="027ae-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="027ae-126">На странице Отложенный или немедленный запрос установите флажок подготовить запрос сейчас, но отправить позже.</span><span class="sxs-lookup"><span data-stu-id="027ae-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="027ae-127">На странице "файл запроса сертификата" введите полный путь и имя файла, в который нужно сохранить запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="027ae-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="027ae-128">На странице "укажите другой шаблон сертификата", чтобы использовать шаблон, отличный от шаблона веб-сервера по умолчанию, установите флажок использовать альтернативный шаблон сертификата для выбранного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="027ae-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="027ae-129">На странице  настроек имени и безопасности  выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="027ae-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="027ae-130">В поле Понятное имя введите отображаемое имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="027ae-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="027ae-131">В качестве битовой длины укажите длину в битах (обычно это значение по умолчанию — 2048).</span><span class="sxs-lookup"><span data-stu-id="027ae-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="027ae-132">Убедитесь, что установлен флажок "помечать закрытый ключ сертификата как экспортируемый"</span><span class="sxs-lookup"><span data-stu-id="027ae-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="027ae-133">На странице "сведения об организации" введите имя Организации и организационное подразделение (например, "подразделение" или "Отдел")</span><span class="sxs-lookup"><span data-stu-id="027ae-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="027ae-134">На странице сведения о географическом расположении укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="027ae-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="027ae-135">На странице имя субъекта/альтернативная тема отображается информация, которая будет автоматически заполнена мастером.</span><span class="sxs-lookup"><span data-stu-id="027ae-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="027ae-136">Если требуются дополнительные альтернативные имена субъектов, их можно указать в следующих двух шагах.</span><span class="sxs-lookup"><span data-stu-id="027ae-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="027ae-137">В параметрах домена SIP на странице "альтернативные имена тем" (SAN) установите флажок домен, чтобы добавить SIP. \<сипдомаин\> элемент в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="027ae-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="027ae-138">На странице "Настройка дополнительных имен для других тем" укажите дополнительные имена для темы, которые необходимы</span><span class="sxs-lookup"><span data-stu-id="027ae-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="027ae-139">Если установлен прокси-сервер КСМПП, по умолчанию доменное имя (например, contoso.com) заполнено в записях сети SAN.</span><span class="sxs-lookup"><span data-stu-id="027ae-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="027ae-140">Если вам нужны дополнительные элементы, добавьте их на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="027ae-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="027ae-141">На странице сводки запроса ознакомьтесь со сведениями о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="027ae-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="027ae-142">После завершения выполнения команд можно просмотреть журнал или нажать кнопку Далее, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="027ae-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="027ae-143">На странице "файл запроса на сертификат" можно просмотреть созданный файл запроса на подписывание сертификата (CSR), щелкнув Просмотреть или выйти из мастера сертификатов, нажав кнопку Готово.</span><span class="sxs-lookup"><span data-stu-id="027ae-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="027ae-144">Скопируйте файл запроса и отправьте его в общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="027ae-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="027ae-145">После получения, импорта и назначения общедоступного сертификата вы должны остановить и перезапустить службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="027ae-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="027ae-146">Для этого введите в консоль управления Lync Server:</span><span class="sxs-lookup"><span data-stu-id="027ae-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. <span data-ttu-id="027ae-147">Чтобы настроить DNS для КСМПП Федерации, добавьте следующую запись SRV для внешнего DNS:\_КСМПП-Server. \_протокол TCP. \<доменное\> имя. SRV-запись будет СОПОСТАВЛЕНа с полным доменным именем EDGE на пограничном сервере с таким же значением порта 5269.</span><span class="sxs-lookup"><span data-stu-id="027ae-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="027ae-148">Кроме того, вы можете настроить запись узла "A" (например, xmpp.contoso.com), указывающую на IP-адрес сервера пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="027ae-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="027ae-149">Если у вас есть пулы EDGE на нескольких сайтах, рекомендуем добавить несколько записей SRV для Федерации КСМПП.</span><span class="sxs-lookup"><span data-stu-id="027ae-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="027ae-150">Добавьте запись SRV для каждого пула пограничного сервера в Организации и назначьте каждому из них другой приоритет.</span><span class="sxs-lookup"><span data-stu-id="027ae-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="027ae-151">Когда все пулы пограничных ресурсов запущены, все запросы КСМПП будут обрабатываться пулом Edge с первым приоритетом, но если этот пул пограничного пула выходит из него, вам не нужно будет добавить новую запись SRV для восстановления функций Федерации КСМПП.</span><span class="sxs-lookup"><span data-stu-id="027ae-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="027ae-152">Настройте новую политику внешнего доступа, чтобы включить всех пользователей, открыв командную консоль Lync Server Management Shell на интерфейсе и введя:</span><span class="sxs-lookup"><span data-stu-id="027ae-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="027ae-153">Включите КСМПП Access для внешних пользователей, введя:</span><span class="sxs-lookup"><span data-stu-id="027ae-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="027ae-154">На пограничном сервере, на котором развернут прокси-сервер КСМПП, откройте командную строку или интерфейс командной строки Windows PowerShell™ и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="027ae-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="027ae-155">Команда **netstat – АНО** — команда Network Statistics, запрос Parameters **— АНО** , который выводит все подключения и прослушиваемые порты, адреса и порты, отображаются в числовой форме и сопоставляются идентификаторы процесса-владельца с каждым соединением.</span><span class="sxs-lookup"><span data-stu-id="027ae-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="027ae-156">Символ **|** определяет канал к следующей команде, **команде findstr**или строке поиска.</span><span class="sxs-lookup"><span data-stu-id="027ae-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="027ae-157">Число 5269 и 23456, которое передается в findstr как параметр, дает команду findstr для поиска в выходных данных средства netstat для строк 5269 и 23456.</span><span class="sxs-lookup"><span data-stu-id="027ae-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="027ae-158">Если КСМПП настроен правильно, результатом команд должно стать прослушивание и установление подключений как на внешнем (порт 5269), так и на внутреннем интерфейсе (порт 23456) пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="027ae-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="027ae-159">Если команды не возвращают установленные и прослушиваемые порты в 5269 и 23456, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="027ae-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="027ae-160">Устранение неполадок Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="027ae-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="027ae-161">Чтобы определить, запущен ли прокси-сервер КСМПП, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="027ae-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="027ae-162">Войдите на пограничный сервер, на котором запущена служба прокси КСМПП, в качестве участника группы локального администратора.</span><span class="sxs-lookup"><span data-stu-id="027ae-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="027ae-163">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — **службы** .</span><span class="sxs-lookup"><span data-stu-id="027ae-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="027ae-164">В службах найдите сервер Lync Server КСМПП reтрансляция прокси-сервера шлюза.</span><span class="sxs-lookup"><span data-stu-id="027ae-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="027ae-165">Служба должна находиться в состоянии " **начато** ".</span><span class="sxs-lookup"><span data-stu-id="027ae-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="027ae-166">Если он еще не запущен, щелкните значок **Пуск** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="027ae-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="027ae-167">Значок отображается как зеленая стрелка, направленная вправо.</span><span class="sxs-lookup"><span data-stu-id="027ae-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="027ae-168">Убедитесь, что служба изменилась на \*\*\*\*"начато".</span><span class="sxs-lookup"><span data-stu-id="027ae-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="027ae-169">Если он успешно запущен, закройте **службы** и продолжайте.</span><span class="sxs-lookup"><span data-stu-id="027ae-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="027ae-170">Если служба сер не была успешно запущена, в разделе средства администрирования откройте окно просмотра событий и просмотрите сообщения об ошибках и предупреждениях на **сервере Lync Server** в **журналах приложений и служб**.</span><span class="sxs-lookup"><span data-stu-id="027ae-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="027ae-171">После запуска службы **перевода КСМПП сервера Lync Server** проверьте, какие команды netstat использовались ранее.</span><span class="sxs-lookup"><span data-stu-id="027ae-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="027ae-172">Если вы не видите установленные и прослушиваемые сеансы, убедитесь, что **маршрут Федерации КСМПП** правильно настроен в построителе топологии</span><span class="sxs-lookup"><span data-stu-id="027ae-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="027ae-173">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="027ae-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="027ae-174">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="027ae-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="027ae-175">В построителе топологии выберите сайт для маршрута Федерации КСМПП и проверьте, отображается ли для него **назначение маршрутов Федерации сайтов** для **КСМПП Федерации** , что вы выбрали назначение маршрута Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="027ae-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="027ae-176">Если назначение маршрута неверно или не задано, щелкните его правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="027ae-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="027ae-177">Установите флажок Федерация КСМПП и выберите правильный пограничный сервер или пул Edge.</span><span class="sxs-lookup"><span data-stu-id="027ae-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="027ae-178">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="027ae-178">Publish the topology.</span></span> <span data-ttu-id="027ae-179">Подробные сведения можно найти [в разделе Публикация топологии в Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="027ae-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="027ae-180">Хотя это не обязательно и не требуется, возможно, потребуется перезапустить серверы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="027ae-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="027ae-181">С помощью процесса netstat, который использовался ранее, убедитесь в том, что пограничный сервер прослушивает или установил сеансы на порте 5269 и порт 23456.</span><span class="sxs-lookup"><span data-stu-id="027ae-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="027ae-182">Если вы по-прежнему не видите ожидаемые сеансы, проверьте, не отображаются ли в окне просмотра событий возможные причины проблем с подключением.</span><span class="sxs-lookup"><span data-stu-id="027ae-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="027ae-183">См. также</span><span class="sxs-lookup"><span data-stu-id="027ae-183">See Also</span></span>


[<span data-ttu-id="027ae-184">Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk</span><span class="sxs-lookup"><span data-stu-id="027ae-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="027ae-185">Управление федеративными XMPP-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="027ae-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

