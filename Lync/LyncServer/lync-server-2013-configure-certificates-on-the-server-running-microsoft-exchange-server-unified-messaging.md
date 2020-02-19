---
title: 'Lync Server 2013: Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="5958d-102">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5958d-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5958d-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="5958d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="5958d-104">Если вы развернули единую систему обмена сообщениями Exchange (UM), как описано в статье [Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) в документации по планированию и хотите предоставить функции единой системы обмена сообщениями Exchange корпоративным голосовым пользователям в вашей организации, вы можете использовать следующие процедуры для настройки сертификата на сервере, на котором работает единая система обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="5958d-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5958d-105">Для внутренних сертификатов на серверах, на которых работает Lync Server 2013 и серверы Microsoft Exchange, должны быть Доверенные корневые сертификаты доверенного корневого центра.</span><span class="sxs-lookup"><span data-stu-id="5958d-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="5958d-106">Может использоваться один и тот же или разные центры сертификации, но корневой сертификат центра сертификации (CA) на серверах должен быть зарегистрирован в хранилище доверенных корневых сертификатов ЦС.</span><span class="sxs-lookup"><span data-stu-id="5958d-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="5958d-107">Для подключения к Lync Server 2013 необходимо настроить сервер Exchange с помощью сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="5958d-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="5958d-108">Загрузите сертификат ЦС для сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="5958d-109">Установите сертификат ЦС для сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="5958d-110">Убедитесь в том, что ЦС включен в список доверенных корневых ЦС сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="5958d-111">Создайте запрос сертификата для сервера Exchange Server и установите сертификат.</span><span class="sxs-lookup"><span data-stu-id="5958d-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="5958d-112">Назначьте сертификат серверу Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="5958d-113">Загрузка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="5958d-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="5958d-114">На сервере единой системы обмена сообщениями Exchange нажмите кнопку **Пуск**, выберите пункт **выполнить**, введите **http://\<имя сервера\>выдающего ЦС/certsrv**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5958d-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="5958d-115">В списке **Выберите задачу** выберите пункт **Загрузка сертификата ЦС, цепочки сертификатов или CRL**.</span><span class="sxs-lookup"><span data-stu-id="5958d-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="5958d-116">В окне **Загрузка сертификата ЦС, цепочки сертификатов или CRL** выберите пункт **Метод шифрования Base 64** и нажмите кнопку **Загрузка сертификата ЦС**.</span><span class="sxs-lookup"><span data-stu-id="5958d-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5958d-p102">На этом этапе вы можете задать шифрование DER. Если вы выбрали шифрование DER, то в следующем шаге процедуры, а также в шаге 10 <STRONG>Установка сертификата ЦС</STRONG> вместо типа файла CER будет использоваться тип P7B.</span><span class="sxs-lookup"><span data-stu-id="5958d-p102">You can also specify Distinguished Encoding Rules (DER) encoding at this step. If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="5958d-p103">В диалоговом окне **Загрузка файла** нажмите кнопку **Сохранить** и сохраните файл на жесткий диск на сервере. (Файл будет иметь расширение CER или P7B в зависимости от выбранного ранее метода шифрования.)</span><span class="sxs-lookup"><span data-stu-id="5958d-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="5958d-121">Установка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="5958d-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="5958d-122">На сервере с единой системой обмена сообщениями Exchange откройте консоль управления (MMC), нажав кнопку **Пуск**, выбрав пункт **выполнить**, введите **MMC** в поле **Открыть** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5958d-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="5958d-123">В меню **Файл** выберите команду **Добавить или удалить оснастку** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5958d-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="5958d-124">В окне **Добавить изолированную оснастку** выберите пункт **Сертификаты** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5958d-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="5958d-125">В диалоговом окне **Оснастка диспетчера сертификатов** выберите пункт **Учетная запись компьютера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5958d-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="5958d-126">В диалоговом окне **Выбор компьютера** убедитесь в том, что установлен флажок **Локальный компьютер (на котором запущена эта консоль)**, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5958d-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="5958d-127">Нажмите кнопку **Закрыть**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5958d-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="5958d-128">В дереве консоли разверните узел **Сертификаты (локальный компьютер)**, узел **Доверенные корневые центры сертификации** и щелкните папку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="5958d-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="5958d-129">Щелкните папку **Сертификаты** правой кнопкой мыши, наведите указатель на пункт **Все задачи** и выберите команду **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="5958d-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="5958d-130">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5958d-130">Click **Next**.</span></span>

10. <span data-ttu-id="5958d-p104">Нажмите кнопку **Обзор**, чтобы выбрать файл, после чего нажмите кнопку **Далее**. (Файл будет иметь расширение CER или P7B в зависимости от метода шифрования, выбранного в шаге 3 раздела **Загрузка сертификата ЦС**).</span><span class="sxs-lookup"><span data-stu-id="5958d-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="5958d-133">Щелкните **Поместить все сертификаты в следующее хранилище**.</span><span class="sxs-lookup"><span data-stu-id="5958d-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="5958d-134">Нажмите кнопку **Обзор** и выберите элемент **Доверенные корневые центры сертификации**.</span><span class="sxs-lookup"><span data-stu-id="5958d-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="5958d-135">Нажмите кнопку **Далее**, чтобы проверить параметры, после чего нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5958d-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="5958d-136">Проверка того, включен ли ЦС в список доверенных корневых ЦС</span><span class="sxs-lookup"><span data-stu-id="5958d-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="5958d-137">На сервере единой системы обмена сообщениями Exchange в консоли MMC разверните узел **Сертификаты (локальный компьютер)**, разверните узел **Доверенные корневые центры сертификации**и нажмите кнопку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="5958d-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="5958d-138">В области сведений проверьте, имеется ли ЦС в списке доверенных ЦС.</span><span class="sxs-lookup"><span data-stu-id="5958d-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="5958d-139">Настройка Exchange Server 2013 UM с Lync Server</span><span class="sxs-lookup"><span data-stu-id="5958d-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="5958d-140">Дополнительные сведения: "Интеграция Exchange 2013 единой системы обмена сообщениями с Lync Server" в документации по [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)Exchange Server по адресу.</span><span class="sxs-lookup"><span data-stu-id="5958d-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="5958d-141">Создание запроса сертификата и установка сертификата на сервере Exchange Server 2007 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="5958d-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="5958d-142">На сервере единой системы обмена сообщениями Exchange нажмите кнопку **Пуск**, выберите пункт **выполнить**, введите **\<http://** имя сервера**\>** выдающего ЦС/certsrv и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5958d-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="5958d-143">В списке **Выберите задачу** выберите пункт **Запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="5958d-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="5958d-144">В окне **Запрос сертификата** щелкните **Расширенный запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="5958d-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="5958d-145">В окне **Расширенный запрос сертификата** щелкните **Создать и выдать запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="5958d-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="5958d-146">В списке **Расширенный запрос сертификата** выберите пункт **Веб-сервер** или другой шаблон сертификата сервера, настроенный для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="5958d-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="5958d-147">В разделе **Идентифицирующие сведения для автономного шаблона** в поле **Имя** введите полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5958d-148">Чтобы обеспечить обмен данными, необходимо ввести полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="5958d-149">В разделе **Параметры ключа** установите флажок **Использовать локальное хранилище компьютера для сертификата**.</span><span class="sxs-lookup"><span data-stu-id="5958d-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="5958d-150">В нижней части веб-страницы нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="5958d-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="5958d-151">В диалоговом окне с запросом на подтверждение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5958d-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="5958d-152">На странице "Сертификат выдан" в разделе **Сертификат выдан** щелкните **Установить этот сертификат**.</span><span class="sxs-lookup"><span data-stu-id="5958d-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="5958d-153">В диалоговом окне с запросом на подтверждение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5958d-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="5958d-154">Убедитесь в том, что появилось сообщение "Новый сертификат успешно установлен".</span><span class="sxs-lookup"><span data-stu-id="5958d-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="5958d-155">Создание сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="5958d-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="5958d-156">Выполните вход на сервер единой системы обмена сообщениями Exchange с соответствующими правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="5958d-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="5958d-157">Дополнительные сведения см. в [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)разделе "разрешения клиентского доступа".</span><span class="sxs-lookup"><span data-stu-id="5958d-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="5958d-158">Чтобы создать сертификат, обратитесь к следующим разделам:</span><span class="sxs-lookup"><span data-stu-id="5958d-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="5958d-159">"Создать новый сертификат Exchange" по адресу[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="5958d-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="5958d-160">"Импорт сертификата Exchange" по адресу[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="5958d-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5958d-161">Чтобы обеспечить обмен данными, в поле <STRONG>Имя субъекта</STRONG> сертификата нужно ввести полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5958d-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="5958d-162">Назначение сертификата на сервере Exchange Server 2007 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="5958d-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="5958d-163">Откройте консоль управления Exchange на сервере, на котором работает единая система обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="5958d-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="5958d-164">В дереве консоли разверните узел **Личные** и щелкните папку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="5958d-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="5958d-165">В области сведений найдите личный сертификат.</span><span class="sxs-lookup"><span data-stu-id="5958d-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="5958d-166">Дважды щелкните сертификат, чтобы просмотреть его данные и проверить, действителен ли он.</span><span class="sxs-lookup"><span data-stu-id="5958d-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5958d-167">Прежде чем сертификат отобразится как действительный, может пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5958d-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="5958d-168">Перезапустите службу единой системы обмена сообщениями Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="5958d-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5958d-169">Сервер, на котором выполняется единая система обмена сообщениями Exchange Server 2007 с пакетом обновления 1 (SP1), автоматически извлекает правильный сертификат.</span><span class="sxs-lookup"><span data-stu-id="5958d-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="5958d-170">Откройте средство просмотра событий и найдите событие с кодом 1112, в котором указано, какой сертификат извлек сервер единой системы обмена сообщениями Exchange Server 2007 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="5958d-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="5958d-171">Назначение сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="5958d-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="5958d-172">Выполните вход на сервер единой системы обмена сообщениями Exchange с соответствующими правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="5958d-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="5958d-173">Дополнительные сведения см. в [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)разделе "разрешения клиентского доступа".</span><span class="sxs-lookup"><span data-stu-id="5958d-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="5958d-174">Процедура назначения сертификата приведена в [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)разделе "назначение служб сертификату".</span><span class="sxs-lookup"><span data-stu-id="5958d-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

