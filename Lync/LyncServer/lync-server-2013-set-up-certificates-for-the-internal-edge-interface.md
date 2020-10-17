---
title: 'Lync Server 2013: Настройка сертификатов для внутреннего интерфейса пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f8c5c41eba828cb6514ba6963167d708ed203d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509896"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="e9a88-102">Настройка сертификатов для внутреннего интерфейса пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9a88-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9a88-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e9a88-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9a88-104">При запуске мастера сертификатов следует убедиться, что вход выполнен с использованием учетной записи, являющейся членом группы, которой назначены соответствующие разрешения для используемого шаблона сертификата.</span><span class="sxs-lookup"><span data-stu-id="e9a88-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="e9a88-105">По умолчанию запрос сертификата Lync Server 2013 будет использовать шаблон сертификата веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="e9a88-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="e9a88-106">Если для запроса на сертификат с помощью этого шаблона вы используете учетную запись, которая является членом группы RTCUniversalServerAdmins, убедитесь, что группе назначены разрешения для регистрации, требуемые для использования этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="e9a88-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="e9a88-p102">Для внутреннего интерфейса каждого пограничного сервера требуется один сертификат. Сертификаты для внутреннего интерфейса могут выдаваться внутренним центром сертификации (ЦС) предприятия или общедоступным ЦС. Если на вашем предприятии развернут внутренний ЦС, то использование внутреннего ЦС вместо общедоступного ЦС для получения сертификата внутреннего интерфейса позволит сэкономить средства. Для создания сертификатов можно использовать внутренний ЦС на базе Windows Server 2008 или Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="e9a88-111">Сведения о данном и других требованиях к сертификатам приведены [в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e9a88-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="e9a88-112">Настройка сертификатов на внутреннем пограничном интерфейсе на уровне сайта состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="e9a88-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="e9a88-113">Загрузка цепочки сертификатов ЦС для внутреннего интерфейса на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e9a88-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="e9a88-114">Импорт цепочки сертификатов ЦС для внутреннего интерфейса на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e9a88-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="e9a88-115">Создание запроса на сертификат для внутреннего интерфейса на одном пограничном сервере, называемом первым пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="e9a88-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="e9a88-116">Импорт сертификата для внутреннего интерфейса на первом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e9a88-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="e9a88-117">Импорт сертификата на остальных пограничных серверах этого сайта или серверах, развернутых за балансировщиком нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e9a88-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="e9a88-118">Назначение сертификата для внутреннего интерфейса каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9a88-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="e9a88-119">При наличии нескольких сайтов с пограничными серверами (т. е. пограничной топологии с несколькими сайтами) или отдельных наборов пограничных серверов, развернутых за разными балансировщиками нагрузки, вам потребуется выполнить этапы, описанные в этом разделе, на каждом сайте с пограничными серверами или для каждого набора пограничных серверов, развернутых за разными балансировщиками нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e9a88-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9a88-120">Действия, описанные в этом разделе, основаны на использовании &nbsp; центра сертификации Windows server 2008, центра сертификации Windows server &nbsp; 2008 &nbsp; R2, центра сертификации Windows Server 2012 или центра сертификации Windows Server 2012 R2 для создания сертификата для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9a88-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="e9a88-121">Для получения инструкций по другим ЦС обратитесь к соответствующей документации.</span><span class="sxs-lookup"><span data-stu-id="e9a88-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="e9a88-122">По умолчанию все пользователи, прошедшие проверку подлинности, имеют соответствующие права для запросов на сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e9a88-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="e9a88-p104">В процедурах, описанных в этом разделе, предполагается, что запросы на сертификаты создаются на пограничном сервере в ходе его развертывания. Для создания запросов на сертификаты можно использовать сервер переднего плана. Этот способ позволяет создавать запросы на сертификаты перед развертыванием пограничных серверов. Перед созданием запросов на сертификаты с помощью сервера переднего плана убедитесь, что запрашиваемый сертификат определен с закрытым ключом, поддерживающим экспорт.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="e9a88-p105">В этом разделе описывается использование CER-файла и P7B-файла для сертификата. Если вы используете файлы с другим расширением, измените процедуры соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="e9a88-129">Загрузка CA цепочки сертификатов для внутреннего интерфейса с использованием веб-сайта certsrv</span><span class="sxs-lookup"><span data-stu-id="e9a88-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="e9a88-130">Войдите на сервер Lync Server 2013 во внутренней сети (то есть не на пограничный сервер) в качестве участника группы **администраторов** .</span><span class="sxs-lookup"><span data-stu-id="e9a88-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="e9a88-131">Щелкните **Пуск**, **Выполнить** и затем введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9a88-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="e9a88-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="e9a88-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9a88-133">Если вы используете ЦС предприятия на базе Windows Server 2008 или Windows Server 2008 R2, то вместо протокола HTTP вам потребуется использовать протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9a88-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="e9a88-134">На веб-странице certsrv выдающего ЦС в списке **Выберите нужное действие** щелкните **Загрузка сертификата ЦС, цепочки сертификатов или CRL**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="e9a88-135">В **Загрузка сертификата ЦС, цепочки сертификатов или CRL** щелкните **Загрузка цепочки сертификатов ЦС**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="e9a88-136">В диалоговом окне **Загрузка файла** щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="e9a88-137">Сохраните файл с расширением P7B на жестком диске сервера и затем скопируйте его на каждый пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="e9a88-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9a88-p106">P7B-файл содержит все сертификаты, находящиеся в пути сертификации. Чтобы просмотреть путь сертификации, откройте сертификат сервера и щелкните путь сертификации.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="e9a88-140">Экспорт цепочки сертификатов ЦС для внутреннего интерфейса с помощью MMC</span><span class="sxs-lookup"><span data-stu-id="e9a88-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="e9a88-141">Вы можете экспортировать корневой сертификат ЦС из любого компьютера, присоединенного к домену, с помощью консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="e9a88-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="e9a88-142">Щелкните **Пуск**, выберите **Выполнить**, а затем введите **MMC**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="e9a88-143">В консоли MMC щелкните **Файл** и выберите **Добавить/удалить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="e9a88-p108">В списке диалогового окна **Добавление и удаление оснастки** выберите **Сертификаты**, а затем нажмите кнопку **Добавить**. При выводе запроса выберите **Учетная запись компьютера**. В диалоговом окне **Выбор компьютера** выберите **Локальный компьютер**. Нажмите кнопку **Готово**. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="e9a88-p109">Разверните узел **Сертификаты (локальный компьютер)**. Разверните узел **Доверенные корневые центры сертификации** и выберите **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="e9a88-p110">Щелкните корневой сертификат, выпущенный вашим ЦС. Щелкните правой кнопкой мыши этот сертификат, выберите **Все задачи**, а затем — **Экспорт**. Откроется **мастер экспорта сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="e9a88-154">В **мастере экспорта сертификатов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="e9a88-155">В диалоговом окне **Формат экспортируемого файла** выберите формат файла, в который будет выполняться экспорт.</span><span class="sxs-lookup"><span data-stu-id="e9a88-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="e9a88-156">Мы рекомендуем использовать **стандартный синтаксис криптографических сообщений: \# Сертификаты PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="e9a88-157">Если вы выбираете **стандартный синтаксис криптографических сообщений: \# Сертификаты PKCS 7 (. P7B)** установите флажок **включить все сертификаты в путь сертификации (если возможно** ) для экспорта цепочки сертификатов, включая сертификат корневого центра сертификации и все сертификаты промежуточного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="e9a88-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="e9a88-158">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-158">Click **Next**.</span></span>

8.  <span data-ttu-id="e9a88-p112">В диалоговом окне **Имя файла экспорта** в поле ввода имени файла введите соответствующий путь и имя файла (расширением имени по умолчанию является P7B) для экспорта сертификата. При желании нажмите кнопку **Обзор**, определите расположение каталога, в котором будет размещаться экспортированный сертификат и введите имя этого сертификата. Нажмите кнопку **Сохранить**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="e9a88-p113">Просмотрите сводку действий и нажмите кнопку **Готово**, чтобы завершить экспорт сертификата. Нажмите кнопку **ОК**, чтобы подтвердить успешное выполнение экспорта.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="e9a88-165">Импорт цепочки сертификатов ЦС для внутреннего интерфейса</span><span class="sxs-lookup"><span data-stu-id="e9a88-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="e9a88-166">На каждом пограничном сервере откройте консоль управления (MMC). Для этого нажмите кнопку **Пуск**, щелкните **Выполнить**, введите **mmc** в поле **Открыть** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="e9a88-167">В меню **Файл** щелкните **Добавить или удалить оснастку** и затем щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="e9a88-168">В окне **Добавить изолированную оснастку** выберите пункт **Сертификаты** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="e9a88-169">В диалоговом окне **Оснастка сертификата** выберите **Учетная запись компьютера** и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="e9a88-170">В диалоговом окне **Выбор компьютера** установите переключатель **Локальный компьютер: (компьютер, на котором выполняется эта консоль)** и затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="e9a88-171">Нажмите кнопку **Закрыть**, а затем — **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="e9a88-172">В дереве консоли разверните **Сертификаты (локальный компьютер)**, щелкните правой кнопкой мыши **Доверенные корневые центры сертификации**, выберите **Все задачи**, а затем — **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="e9a88-173">В поле **Импортируемый файл** укажите имя файла сертификата (т. е. имя, которое вы указали при загрузке цепочки сертификатов ЦС для внутреннего интерфейса на предыдущем шаге).</span><span class="sxs-lookup"><span data-stu-id="e9a88-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="e9a88-174">Повторите эту процедуру на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e9a88-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="e9a88-175">Создание запроса на сертификат для внутреннего интерфейса</span><span class="sxs-lookup"><span data-stu-id="e9a88-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="e9a88-176">На одном из пограничных серверов запустите мастер развертывания и напротив **Шаг 3. Запрос, установка или назначение сертификатов** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9a88-177">При наличии нескольких пограничных серверов в одном расположении пула вы можете запускать мастер сертификатов на любом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="e9a88-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="e9a88-178">После первичного выполнения шага 3 кнопка изменится на <STRONG>Повторный запуск</STRONG>. После запроса, установки и назначения всех требуемых сертификатов рядом с кнопкой появится зеленый флажок, указывающий на успешное завершение задачи.</span><span class="sxs-lookup"><span data-stu-id="e9a88-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="e9a88-179">На странице **Доступные задачи для сертификатов** выберите **Создать запрос на сертификат**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="e9a88-180">На странице **Запрос на сертификат** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="e9a88-181">На странице **Отложенные или немедленные запросы** установите переключатель **Подготовить запрос сейчас, чтобы отправить его позже**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="e9a88-182">На странице **файл запроса сертификата** введите полный путь и имя файла, в который будет сохранен запрос (например, **c: \\ CERT \_ internal \_ Edge. cer**).</span><span class="sxs-lookup"><span data-stu-id="e9a88-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="e9a88-183">На странице **Указание альтернативного шаблона сертификата** установите флажок **Использовать альтернативный шаблон сертификата для выбранного ЦС**, чтобы использовать шаблон, отличный от шаблона WebServer по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9a88-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="e9a88-184">На странице **Настройка имени и безопасности** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9a88-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="e9a88-185">В поле **Понятное имя** введите отображаемое имя для сертификата (например, "Внутренняя граница").</span><span class="sxs-lookup"><span data-stu-id="e9a88-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="e9a88-186">В раскрывающемся списке **Длина в битах** укажите длину в битах (как правило, по умолчанию используется значение **2048**).</span><span class="sxs-lookup"><span data-stu-id="e9a88-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9a88-187">Большее высокое значение длины ключа обеспечивает более высокий уровень безопасности, однако негативно сказывается на скорости.</span><span class="sxs-lookup"><span data-stu-id="e9a88-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9a88-188">Если сертификат должен поддерживать экспорт, установите флажок **Закрытый ключ сертификата поддерживает экспорт**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="e9a88-189">На странице **Сведения об организации** введите название организации и подразделения (например, отдела или подразделения).</span><span class="sxs-lookup"><span data-stu-id="e9a88-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="e9a88-190">На странице **Сведения о местоположении** укажите сведения о расположении организации.</span><span class="sxs-lookup"><span data-stu-id="e9a88-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="e9a88-191">На странице **Имя субъекта и альтернативные имена субъекта** отображаются данные, которые заполняются мастером автоматически.</span><span class="sxs-lookup"><span data-stu-id="e9a88-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="e9a88-192">На странице **Настройка дополнительных альтернативных имен субъекта** укажите дополнительные альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="e9a88-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="e9a88-193">На странице **Сводка по запросу** проверьте сведения о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="e9a88-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="e9a88-194">После завершения выполнения команд выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9a88-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="e9a88-195">Чтобы просмотреть журнал запросов на сертификаты, щелкните **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="e9a88-196">Чтобы завершить запрос на сертификат, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="e9a88-197">На странице **Certificate Request File (Файл запроса сертификата)** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9a88-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="e9a88-198">Чтобы просмотреть файл запроса подписи сертификата (CSR-файл), нажмите кнопку **View (Просмотр)**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="e9a88-199">Чтобы закрыть мастер, щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="e9a88-200">Отправьте этот файл в ЦС (по электронной почте или с помощью другого метода, поддерживаемого для вашего ЦС предприятия) и затем при получении файла ответа скопируйте новый сертификат на этот компьютер, чтобы он был доступен для импорта.</span><span class="sxs-lookup"><span data-stu-id="e9a88-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="e9a88-201">Импорт сертификата для внутреннего интерфейса</span><span class="sxs-lookup"><span data-stu-id="e9a88-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="e9a88-202">Выполните вход на пограничный сервер, используемый для создания запроса на сертификат, в качестве члена локальной группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="e9a88-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="e9a88-203">В мастере развертывания нажмите кнопку **Повторный запуск** напротив строки **Шаг 3. Запрос, установка или назначение сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="e9a88-204">После первичного выполнения шага 3 кнопка изменяется на **Повторный запуск**. Однако зеленый флажок, указывающий на успешное завершение задачи, появляется только после запроса, установки и назначения всех требуемых сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e9a88-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="e9a88-205">На странице **Доступные задачи для сертификатов** щелкните **Импортировать сертификат из P7B-, PFX- или CER-файла**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="e9a88-206">На странице **Импорт сертификата** введите полный путь и имя файла сертификата, который был запрошен или получен для внутреннего интерфейса этого пограничного сервера (или щелкните **Обзор**, чтобы найти и выбрать файл).</span><span class="sxs-lookup"><span data-stu-id="e9a88-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="e9a88-207">Если вы импортируете сертификат, содержащий закрытый ключ, для остальных членов пула, то установите флажок **Файл сертификата содержит закрытый ключ сертификата** и укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="e9a88-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="e9a88-208">Экспорт сертификата с закрытым ключом для пограничных серверов пула</span><span class="sxs-lookup"><span data-stu-id="e9a88-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="e9a88-209">Войдите как член группы администраторов на тот же пограничный сервер, на котором выполнялся импорт сертификата.</span><span class="sxs-lookup"><span data-stu-id="e9a88-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="e9a88-210">Щелкните **Пуск**, **Выполнить** и введите **MMC**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="e9a88-211">В консоли MMC выберите **Файл** и затем выберите **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="e9a88-212">На странице "Добавление и удаление оснастки" щелкните **Сертификаты** и затем **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="e9a88-p114">В диалоговом окне "Оснастка сертификатов" выберите **Учетная запись компьютера**. Нажмите кнопку **Далее**. В диалоговом окне "Выбор компьютера" установите флажок **Локальный компьютер: (компьютер, на котором выполняется эта консоль)**. Чтобы завершить настройку консоли MMC, щелкните **Готово** и **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="e9a88-p115">Чтобы развернуть хранилища сертификатов, дважды щелкните **Сертификаты (локальный компьютер)**. Дважды щелкните **Личные** и затем дважды щелкните **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e9a88-p116">Если в хранилище личных сертификатов для локального компьютера сертификат отсутствует, то закрытый ключ, связанный с сертификатом, не был импортирован. Проверьте запрос и шаги, относящиеся к импорту. Если проблема повторится, обратитесь к администратору или поставщику ЦС.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="e9a88-p117">В хранилище личных сертификатов для локального компьютера щелкните правой кнопкой мыши сертификат, который необходимо экспортировать. Щелкните **Все задачи**, а затем — **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="e9a88-p118">В мастере экспорта сертификатов нажмите кнопку **Далее**. Установите переключатель **Да, экспортировать закрытый ключ**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9a88-p119">Если переключатель <STRONG>Да, экспортировать закрытый ключ</STRONG> недоступен, то закрытый ключ, связанный с этим сертификатом, не был помечен для экспорта. В этом случае вам потребуется запросить сертификат повторно и проверить, помечен ли сертификат для экспорта закрытого ключа. Обратитесь к администратору или поставщику ЦС.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="e9a88-231">В диалоговом окне Экспорт форматов файлов выберите файл **обмена личной информацией — PKCS \# 12 (. PFX)** , а затем выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="e9a88-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="e9a88-232">Включить по возможности все сертификаты в путь сертификата.</span><span class="sxs-lookup"><span data-stu-id="e9a88-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="e9a88-233">Экспортировать все расширенные свойства.</span><span class="sxs-lookup"><span data-stu-id="e9a88-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="e9a88-p120">При экспорте сертификата с пограничного сервера не устанавливайте флажок <STRONG>Удалить закрытый ключ после успешного экспорта</STRONG>. В противном случае потребуется импортировать сертификат и закрытый ключ на этот пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="e9a88-236">Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="e9a88-p121">Если вы хотите назначить пароль для обеспечения защиты закрытого ключа, введите пароль и его подтверждение для закрытого ключа. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="e9a88-p122">Введите путь к экспортируемому сертификату, включая имя и расширение файла (PFX). Путь должен быть доступен всем пограничным серверам пула или доступен с помощью съемных носителей, например USB-устройства флэш-памяти. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="e9a88-p123">Проверьте сводные данные на странице "Завершение мастера экспорта сертификатов". Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="e9a88-245">В диалоговом окне успешного завершения экспорта нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="e9a88-246">Импортируйте экспортированный файл сертификата на другие пограничные серверы, выполнив действия, описанные в разделе [Настройка сертификатов для внешнего интерфейса пограничного сервера для процедур Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9a88-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="e9a88-247">Назначение внутреннего сертификата на пограничных серверах</span><span class="sxs-lookup"><span data-stu-id="e9a88-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="e9a88-248">В мастере развертывания каждого пограничного сервера нажмите кнопку **Повторный запуск** напротив строки **Шаг 3. Запрос, установка или назначение сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="e9a88-249">На странице **Доступные задачи для сертификатов** выберите **Назначить имеющийся сертификат**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="e9a88-250">На странице **Назначение сертификата** выберите **Внутренний интерфейс пограничного сервера**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="e9a88-251">На странице **Хранилище сертификатов** выберите сертификат, который был импортирован для внутреннего интерфейса пограничного сервера (на предыдущем шаге).</span><span class="sxs-lookup"><span data-stu-id="e9a88-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="e9a88-252">На странице **Сводка по назначению сертификата** проверьте параметры и затем нажмите кнопку **Далее**, чтобы назначить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e9a88-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="e9a88-253">На странице завершения работы мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e9a88-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="e9a88-254">После завершения этой процедуры для назначения сертификата внутреннего интерфейса пограничного сервера откройте оснастку "Сертификаты" на каждом сервере, разверните узлы **Сертификаты (локальный компьютер)** и **Личные**, а затем щелкните **Сертификаты**. Убедитесь, что области сведений указан сертификат внутреннего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9a88-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="e9a88-255">Если ваше развертывание содержит несколько пограничных серверов, повторите эту процедуру для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9a88-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

