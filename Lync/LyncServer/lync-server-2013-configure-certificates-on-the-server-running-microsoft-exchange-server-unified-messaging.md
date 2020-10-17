---
title: 'Lync Server 2013: Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server'
description: 'Lync Server 2013: Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server.'
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
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564405"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="8ee4e-103">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8ee4e-103">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee4e-104">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="8ee4e-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="8ee4e-105">Если вы развернули единую систему обмена сообщениями Exchange (UM), как описано в статье [Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) в документации по планированию и хотите предоставить функции единой системы обмена сообщениями Exchange корпоративным голосовым пользователям в вашей организации, вы можете использовать следующие процедуры для настройки сертификата на сервере, на котором работает единая система обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-105">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ee4e-106">Для внутренних сертификатов на серверах, на которых работает Lync Server 2013 и серверы Microsoft Exchange, должны быть Доверенные корневые сертификаты доверенного корневого центра.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-106">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="8ee4e-107">Может использоваться один и тот же или разные центры сертификации, но корневой сертификат центра сертификации (CA) на серверах должен быть зарегистрирован в хранилище доверенных корневых сертификатов ЦС.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-107">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="8ee4e-108">Для подключения к Lync Server 2013 необходимо настроить сервер Exchange с помощью сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-108">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="8ee4e-109">Загрузите сертификат ЦС для сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-109">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="8ee4e-110">Установите сертификат ЦС для сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-110">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="8ee4e-111">Убедитесь в том, что ЦС включен в список доверенных корневых ЦС сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-111">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="8ee4e-112">Создайте запрос сертификата для сервера Exchange Server и установите сертификат.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-112">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="8ee4e-113">Назначьте сертификат серверу Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-113">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="8ee4e-114">Загрузка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="8ee4e-114">To download the CA certificate</span></span>

1.  <span data-ttu-id="8ee4e-115">На сервере с единой системой обмена сообщениями Exchange нажмите кнопку **Пуск**, выберите пункт **выполнить**, введите **http:// \<name of your Issuing CA Server\> /certsrv**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-115">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="8ee4e-116">В списке **Выберите задачу** выберите пункт **Загрузка сертификата ЦС, цепочки сертификатов или CRL**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-116">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="8ee4e-117">В окне **Загрузка сертификата ЦС, цепочки сертификатов или CRL** выберите пункт **Метод шифрования Base 64** и нажмите кнопку **Загрузка сертификата ЦС**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-117">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ee4e-p102">На этом этапе вы можете задать шифрование DER. Если вы выбрали шифрование DER, то в следующем шаге процедуры, а также в шаге 10 <STRONG>Установка сертификата ЦС</STRONG> вместо типа файла CER будет использоваться тип P7B.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-p102">You can also specify Distinguished Encoding Rules (DER) encoding at this step. If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="8ee4e-p103">В диалоговом окне **Загрузка файла** нажмите кнопку **Сохранить** и сохраните файл на жесткий диск на сервере. (Файл будет иметь расширение CER или P7B в зависимости от выбранного ранее метода шифрования.)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="8ee4e-122">Установка сертификата ЦС</span><span class="sxs-lookup"><span data-stu-id="8ee4e-122">To install the CA certificate</span></span>

1.  <span data-ttu-id="8ee4e-123">На сервере с единой системой обмена сообщениями Exchange откройте консоль управления (MMC), нажав кнопку **Пуск**, выбрав пункт **выполнить**, введите **MMC** в поле **Открыть** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-123">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="8ee4e-124">В меню **Файл** выберите команду **Добавить или удалить оснастку** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-124">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="8ee4e-125">В окне **Добавить изолированную оснастку** выберите пункт **Сертификаты** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-125">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="8ee4e-126">В диалоговом окне **Оснастка диспетчера сертификатов** выберите пункт **Учетная запись компьютера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-126">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="8ee4e-127">В диалоговом окне **Выбор компьютера** убедитесь в том, что установлен флажок **Локальный компьютер (на котором запущена эта консоль)**, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-127">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="8ee4e-128">Нажмите кнопку **Закрыть**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-128">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="8ee4e-129">В дереве консоли разверните узел **Сертификаты (локальный компьютер)**, узел **Доверенные корневые центры сертификации** и щелкните папку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-129">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="8ee4e-130">Щелкните папку **Сертификаты** правой кнопкой мыши, наведите указатель на пункт **Все задачи** и выберите команду **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-130">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="8ee4e-131">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-131">Click **Next**.</span></span>

10. <span data-ttu-id="8ee4e-p104">Нажмите кнопку **Обзор**, чтобы выбрать файл, после чего нажмите кнопку **Далее**. (Файл будет иметь расширение CER или P7B в зависимости от метода шифрования, выбранного в шаге 3 раздела **Загрузка сертификата ЦС**).</span><span class="sxs-lookup"><span data-stu-id="8ee4e-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="8ee4e-134">Щелкните **Поместить все сертификаты в следующее хранилище**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-134">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="8ee4e-135">Нажмите кнопку **Обзор** и выберите элемент **Доверенные корневые центры сертификации**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-135">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="8ee4e-136">Нажмите кнопку **Далее**, чтобы проверить параметры, после чего нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-136">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="8ee4e-137">Проверка того, включен ли ЦС в список доверенных корневых ЦС</span><span class="sxs-lookup"><span data-stu-id="8ee4e-137">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="8ee4e-138">На сервере единой системы обмена сообщениями Exchange в консоли MMC разверните узел **Сертификаты (локальный компьютер)**, разверните узел **Доверенные корневые центры сертификации**и нажмите кнопку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-138">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="8ee4e-139">В области сведений проверьте, имеется ли ЦС в списке доверенных ЦС.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-139">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="8ee4e-140">Настройка Exchange Server 2013 UM с Lync Server</span><span class="sxs-lookup"><span data-stu-id="8ee4e-140">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="8ee4e-141">Дополнительные сведения: "Интеграция Exchange 2013 единой системы обмена сообщениями с Lync Server" в документации по Exchange Server по адресу [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .</span><span class="sxs-lookup"><span data-stu-id="8ee4e-141">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="8ee4e-142">Создание запроса сертификата и установка сертификата на сервере Exchange Server 2007 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-142">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="8ee4e-143">На сервере с единой системой обмена сообщениями Exchange нажмите кнопку **Пуск**, выберите пункт **выполнить**, введите **http:// \<**name of your Issuing CA Server**\> /certsrv**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-143">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<**name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="8ee4e-144">В списке **Выберите задачу** выберите пункт **Запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-144">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="8ee4e-145">В окне **Запрос сертификата** щелкните **Расширенный запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-145">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="8ee4e-146">В окне **Расширенный запрос сертификата** щелкните **Создать и выдать запрос к этому ЦС**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-146">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="8ee4e-147">В списке **Расширенный запрос сертификата** выберите пункт **Веб-сервер** или другой шаблон сертификата сервера, настроенный для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-147">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="8ee4e-148">В разделе **Идентифицирующие сведения для автономного шаблона** в поле **Имя** введите полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-148">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ee4e-149">Чтобы обеспечить обмен данными, необходимо ввести полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-149">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="8ee4e-150">В разделе **Параметры ключа** установите флажок **Использовать локальное хранилище компьютера для сертификата**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-150">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="8ee4e-151">В нижней части веб-страницы нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-151">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="8ee4e-152">В диалоговом окне с запросом на подтверждение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-152">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="8ee4e-153">На странице "Сертификат выдан" в разделе **Сертификат выдан** щелкните **Установить этот сертификат**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-153">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="8ee4e-154">В диалоговом окне с запросом на подтверждение нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-154">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="8ee4e-155">Убедитесь в том, что появилось сообщение "Новый сертификат успешно установлен".</span><span class="sxs-lookup"><span data-stu-id="8ee4e-155">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="8ee4e-156">Создание сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ee4e-156">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="8ee4e-157">Выполните вход на сервер единой системы обмена сообщениями Exchange с соответствующими правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-157">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="8ee4e-158">Дополнительные сведения см. в разделе "разрешения клиентского доступа" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="8ee4e-158">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="8ee4e-159">Чтобы создать сертификат, обратитесь к следующим разделам:</span><span class="sxs-lookup"><span data-stu-id="8ee4e-159">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="8ee4e-160">"Создать новый сертификат Exchange" по адресу [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-160">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="8ee4e-161">"Импорт сертификата Exchange" по адресу [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-161">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ee4e-162">Чтобы обеспечить обмен данными, в поле <STRONG>Имя субъекта</STRONG> сертификата нужно ввести полное доменное имя сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-162">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="8ee4e-163">Назначение сертификата на сервере Exchange Server 2007 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="8ee4e-163">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="8ee4e-164">Откройте консоль управления Exchange на сервере, на котором работает единая система обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-164">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="8ee4e-165">В дереве консоли разверните узел **Личные** и щелкните папку **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-165">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="8ee4e-166">В области сведений найдите личный сертификат.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-166">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="8ee4e-167">Дважды щелкните сертификат, чтобы просмотреть его данные и проверить, действителен ли он.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-167">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ee4e-168">Прежде чем сертификат отобразится как действительный, может пройти несколько минут.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-168">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="8ee4e-169">Перезапустите службу единой системы обмена сообщениями Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-169">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ee4e-170">Сервер, на котором выполняется единая система обмена сообщениями Exchange Server 2007 с пакетом обновления 1 (SP1), автоматически извлекает правильный сертификат.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-170">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="8ee4e-171">Откройте средство просмотра событий и найдите событие с кодом 1112, в котором указано, какой сертификат извлек сервер единой системы обмена сообщениями Exchange Server 2007 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="8ee4e-171">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="8ee4e-172">Назначение сертификата на сервере Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ee4e-172">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="8ee4e-173">Выполните вход на сервер единой системы обмена сообщениями Exchange с соответствующими правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ee4e-173">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="8ee4e-174">Дополнительные сведения см. в разделе "разрешения клиентского доступа" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .</span><span class="sxs-lookup"><span data-stu-id="8ee4e-174">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="8ee4e-175">Процедура назначения сертификата приведена в разделе "назначение служб сертификату" [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .</span><span class="sxs-lookup"><span data-stu-id="8ee4e-175">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

