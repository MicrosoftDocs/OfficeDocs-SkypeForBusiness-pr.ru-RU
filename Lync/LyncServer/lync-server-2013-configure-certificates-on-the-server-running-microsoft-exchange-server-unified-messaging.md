---
title: 'Lync Server 2013: Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями сервера Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="c4b8c-102">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4b8c-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4b8c-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="c4b8c-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="c4b8c-104">Если вы развернули единую систему обмена сообщениями Exchange (UM), как описано в разделе [Планирование интеграции единой системы обмена сообщениями в Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) в документации по планированию, и вы хотите предоставить функции Exchange UM пользователям корпоративной голосовой связи в вашей учетной записи Организации, для настройки сертификата на сервере, на котором запущено приложение Exchange UM, можно использовать описанные ниже процедуры.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4b8c-105">Для внутренних сертификатов оба сервера, на которых запущены приложения Lync Server 2013 и серверы Microsoft Exchange, должны иметь взаимно Доверенные корневые доверенные центры сертификации.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="c4b8c-106">Центр сертификации (ЦС) может быть либо тем же, либо другим центром сертификации, если корневой сертификат центра сертификации зарегистрирован в хранилище сертификатов доверенного корневого центра.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="c4b8c-107">Для подключения к серверу Lync Server 2013 необходимо настроить сервер Exchange с сертификатом сервера.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="c4b8c-108">Скачайте сертификат ЦС для сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="c4b8c-109">Установите сертификат ЦС для сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="c4b8c-110">Убедитесь, что центр сертификации входит в список доверенных корневых ЦС сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="c4b8c-111">Создайте запрос на сертификат для сервера Exchange и установите сертификат.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="c4b8c-112">Назначьте сертификат для сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="c4b8c-113">Загрузка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="c4b8c-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="c4b8c-114">На сервере, на котором работает UM, нажмите кнопку **Пуск**, выберите команду **выполнить**, введите **http://\<имя сервера\>выдающего ЦС/certsrv**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="c4b8c-115">В разделе **выберите задачу**нажмите **загрузить сертификат ЦС, цепочку сертификатов или CRL**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="c4b8c-116">В разделе **Загрузка сертификата ЦС, цепочки сертификатов или CRL**выберите **метод кодирования для базового 64**, а затем нажмите кнопку **загрузить сертификат ЦС**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4b8c-117">Вы также можете задать кодировку DER (правила кодирования) на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="c4b8c-118">Если вы выбрали кодировку DER, тип файла на следующем этапе и на этапе 10 <STRONG>для установки сертификата ЦС</STRONG> —. p7b, а не. cer.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="c4b8c-119">В диалоговом окне **Загрузка файла** нажмите кнопку **сохранить**, а затем сохраните файл на жестком диске сервера.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="c4b8c-120">(В зависимости от кодировки, выбранной на предыдущем шаге, файл будет содержать расширение. cer или. p7b.)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="c4b8c-121">Установка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="c4b8c-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="c4b8c-122">На сервере с Exchange UM откройте консоль управления (MMC), нажав кнопку **Пуск**, выберите команду **выполнить**, введите в поле **Открыть** значение **MMC** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="c4b8c-123">В меню **файл** выберите команду **Добавить или удалить оснастку**, а затем нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="c4b8c-124">В диалоговом окне **Добавление изолированных оснасток** выберите пункт **Сертификаты**и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="c4b8c-125">В диалоговом окне **Оснастка диспетчера сертификатов** выберите **Учетная запись компьютера** и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="c4b8c-126">В диалоговом окне **Выбор компьютера** убедитесь, что на **локальном компьютере установлен флажок (компьютер, на котором запущена эта консоль)** , и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="c4b8c-127">Нажмите кнопку **Закрыть**, а затем — кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="c4b8c-128">В дереве консоли разверните узел **Сертификаты (локальный компьютер)**, а затем разверните узел **Доверенные корневые центры сертификации**и выберите пункт **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="c4b8c-129">Щелкните правой кнопкой мыши пункт **Сертификаты**, выберите пункт **все задачи**и нажмите кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="c4b8c-130">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-130">Click **Next**.</span></span>

10. <span data-ttu-id="c4b8c-131">Нажмите кнопку **Обзор** , чтобы найти файл, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="c4b8c-132">(В зависимости от кодировки, выбранной на этапе 3 **для скачивания сертификата ЦС**, файл будет содержать расширение. cer или. p7b.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="c4b8c-133">Нажмите кнопку **поместить все сертификаты в следующее хранилище**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="c4b8c-134">Нажмите кнопку **Обзор**и выберите пункт **Доверенные корневые центры сертификации**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="c4b8c-135">Нажмите кнопку **Далее** , чтобы проверить настройки, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="c4b8c-136">Проверка того, что центр сертификации входит в список доверенных корневых ЦС</span><span class="sxs-lookup"><span data-stu-id="c4b8c-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="c4b8c-137">На сервере, на котором запущена служба единой системы обмена сообщениями, в MMC разверните раздел **Сертификаты (локальный компьютер)**, разверните узел **Доверенные корневые центры сертификации**и выберите пункт **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="c4b8c-138">В области сведений убедитесь, что ваш центр сертификации входит в список доверенных центров сертификации.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="c4b8c-139">Настройка Exchange Server 2013 UM с Lync Server</span><span class="sxs-lookup"><span data-stu-id="c4b8c-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="c4b8c-140">Подробные сведения можно найти в разделе "Интеграция Exchange 2013 UM с Lync Server" в документации Exchange Server [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)по адресу.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="c4b8c-141">Создание запроса на сертификат и установка сертификата на сервере Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="c4b8c-142">На сервере, на котором работает UM, нажмите кнопку **Пуск**, выберите команду **выполнить**, введите **\<http://** имя сервера**\>** выдающего ЦС/certsrv и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="c4b8c-143">В разделе **выберите задачу**щелкните **запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="c4b8c-144">В разделе **запрос сертификата**щелкните **Расширенный запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="c4b8c-145">В разделе **Расширенный запрос сертификата**выберите команду **создать и отправить запрос этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="c4b8c-146">В разделе **Расширенный запрос сертификата**выберите **веб-сервер** или другой шаблон сертификата сервера, настроенный для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="c4b8c-147">В разделе **идентифицирующая информация для автономного шаблона**в поле **имя** введите полное доменное имя (FQDN) сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4b8c-148">Необходимо ввести полное доменное имя сервера Exchange для работы с данными.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="c4b8c-149">В разделе **Параметры ключа**щелкните **сертификат магазина в хранилище сертификатов локального компьютера** .</span><span class="sxs-lookup"><span data-stu-id="c4b8c-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="c4b8c-150">Нажмите кнопку " **Отправить** " в нижней части веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="c4b8c-151">В открывшемся диалоговом окне с запросом подтверждения нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="c4b8c-152">На странице Сертификат выдан в разделе **сертификат выдан**выберите **установить этот сертификат**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="c4b8c-153">В открывшемся диалоговом окне с запросом подтверждения нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="c4b8c-154">Убедитесь, что на экране появится сообщение "ваш новый сертификат успешно установлен".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="c4b8c-155">Создание сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4b8c-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="c4b8c-156">Войдите на сервер, на котором запущена служба единой системы обмена сообщениями с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="c4b8c-157">Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)разделе "разрешения клиентского доступа".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="c4b8c-158">Чтобы создать сертификат, ознакомьтесь с приведенными ниже инструкциями.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="c4b8c-159">"Создать новый сертификат Exchange" на[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="c4b8c-160">"Импортировать сертификат Exchange" на[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4b8c-161">Для <STRONG>имени субъекта</STRONG>сертификата необходимо ввести полное доменное имя сервера Exchange, чтобы связь работала.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="c4b8c-162">Назначение сертификата на сервере Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="c4b8c-163">На сервере, на котором запущена служба единой системы обмена сообщениями, откройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="c4b8c-164">В дереве консоли разверните узел **Личные** и выберите пункт **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="c4b8c-165">Убедитесь, что в области сведений отображается персональный сертификат.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="c4b8c-166">Дважды щелкните сертификат, чтобы прочитать его сведения, и убедитесь, что он является действительным.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4b8c-167">Для правильного отображения сертификата может пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="c4b8c-168">Перезапустите службу единой системы обмена сообщениями Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4b8c-169">Сервер, на котором работает Exchange Server 2007 с пакетом обновления 1 (SP1), UM автоматически получает правильный сертификат.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="c4b8c-170">Откройте средство просмотра событий и найдите событие с кодом 1112, которое указывает, какой сертификат был извлечен сервером, на котором работает сервер Exchange Server 2007 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="c4b8c-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="c4b8c-171">Назначение сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="c4b8c-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="c4b8c-172">Войдите на сервер, на котором запущена служба единой системы обмена сообщениями с необходимыми правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="c4b8c-173">Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)разделе "разрешения клиентского доступа".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="c4b8c-174">Процедура назначения сертификата приведена в [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)разделе "назначение служб сертификату".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

