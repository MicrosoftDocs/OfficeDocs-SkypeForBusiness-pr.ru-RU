---
title: 'Lync Server 2013: настройка сертификатов для серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="90e4b-102">Настройка сертификатов для серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90e4b-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90e4b-103">_**Тема последнего изменения:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="90e4b-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="90e4b-104">Для успешного выполнения этой процедуры необходимо войти в систему с помощью учетной записи пользователя, который является членом группы Рткуниверсалсерверадминс, или иметь соответствующие разрешения, делегированные.</span><span class="sxs-lookup"><span data-stu-id="90e4b-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="90e4b-105">Дополнительные сведения о делегировании разрешений можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="90e4b-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="90e4b-106">В зависимости от вашей организации и требований для запроса сертификатов может потребоваться участие в других группах.</span><span class="sxs-lookup"><span data-stu-id="90e4b-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="90e4b-107">Обратитесь к группе, управляющей центром сертификации (PKI) инфраструктуры открытых ключей (ЦС).</span><span class="sxs-lookup"><span data-stu-id="90e4b-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90e4b-108">Lync Server 2013 включает в себя поддержку комплекта SHA-2 (SHA-384 256 224 2) для алгоритмов хэширования и подписи для подключений от клиентов, работающих под управлением Windows 7, Windows Server 512 R2, Windows Server 2008, Windows Vista и Операционные системы Windows XP в дополнение к Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="90e4b-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="90e4b-109">Чтобы обеспечить поддержку внешнего доступа с использованием пакета SHA-2, внешний сертификат выпускается общим центром сертификации, который также может выдавать сертификаты для хэша той же длины.</span><span class="sxs-lookup"><span data-stu-id="90e4b-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="90e4b-110">Выбор алгоритма хэширования и подписывания зависит от клиентов и серверов, которые будут использовать данный сертификат, а также других компьютеров и устройств, с которыми будут обмениваться данными эти клиенты и серверы и которым также должен быть известен порядок использования алгоритмов, предусмотренных этим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="90e4b-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="90e4b-111">Сведения о том, какие из этих размеров поддерживаются операционной системой и некоторыми клиентскими приложениями,<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>см.</span><span class="sxs-lookup"><span data-stu-id="90e4b-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="90e4b-112">Каждый сервер Standard Edition или сервер переднего плана должен иметь до четырех сертификатов: сертификат Оаустокениссуер, сертификат по умолчанию, внутренний веб-сертификат, а также внешний сертификат для веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="90e4b-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="90e4b-113">Тем не менее, вы можете запросить и назначить один сертификат по умолчанию для соответствующей записи альтернативного имени субъекта, а также сертификата Оаустокениссуер.</span><span class="sxs-lookup"><span data-stu-id="90e4b-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="90e4b-114">Сведения о требованиях к сертификатам приведены [в разделе Требования к сертификатам внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="90e4b-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="90e4b-115">Подробные сведения о том, как запросить, назначить и установить сертификат Оаустокениссуер, можно найти [в разделе Управление проверкой подлинности серверов (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="90e4b-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="90e4b-116">Используйте описанную ниже процедуру, чтобы запросить, назначить и установить сертификаты сервера Standard Edition или сервера с интерфейсом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="90e4b-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="90e4b-117">Повторите процедуру для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="90e4b-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="90e4b-118">Ниже описано, как настроить сертификаты из внутренней инфраструктуры PKI, развернутой вашей организацией, и с помощью обработки запросов в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="90e4b-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="90e4b-119">Сведения о том, как получать сертификаты из общедоступного центра сертификации, приведены в разделе <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">требования к сертификатам внутренних серверов в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="90e4b-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="90e4b-120">Кроме того, в этой статье описано, как запрашивать, назначать и устанавливать сертификаты во время настройки серверного переднего плана.</span><span class="sxs-lookup"><span data-stu-id="90e4b-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="90e4b-121">Если вы предвернули предварительно запрошенные сертификаты, как описано в разделе " <A href="lync-server-2013-request-certificates-in-advance-optional.md">Предварительные сертификаты" (необязательно) для Lync Server 2013</A> , а также внутренней корпоративной PKI, развернутой в вашей организации, чтобы получить сертификаты, необходимо соответствующим образом изменить эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="90e4b-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="90e4b-122">Настройка сертификатов для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="90e4b-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="90e4b-123">В мастере развертывания Lync Server нажмите кнопку " **выполнить** " рядом с **шагом 3: запрос, установка и назначение сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="90e4b-124">На странице **Мастер сертификатов** щелкните элемент **Запросить**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="90e4b-125">На странице **запроса сертификата** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="90e4b-p107">На странице **Отложенные или немедленные запросы** вы можете принять используемый по умолчанию параметр **Немедленно отправить запрос в локальный центр сертификации**, нажав кнопку **Далее**. В случае выбора этого параметра должен быть доступен внутренний центр сертификации с автоматической регистрацией по сети. Если выбирать задержку запроса, отображается запрос на ввод имени и расположения для сохранения файла запроса на сертификат. Запрос на сертификат должен быть представлен и обработан центром сертификации внутри вашей организации или общим центром сертификации. После этого вам необходимо импортировать ответ сертификата и назначить его подходящей роли сертификата.</span><span class="sxs-lookup"><span data-stu-id="90e4b-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="90e4b-131">На странице **Выбор центра сертификации (ЦС)** выберите в списке **выбрать центр сертификации из списка** , а затем выберите известный (с помощью регистрации в службе доменных служб Active Directory) центр сертификации из списка.</span><span class="sxs-lookup"><span data-stu-id="90e4b-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="90e4b-132">Либо выберите параметр **Указать другой центр сертификации**, введите в поле имя другого центра сертификации и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="90e4b-133">На странице **Учетная запись центра сертификации** требуется ввести учетные данные для запроса сертификата и обработки этого запроса на сертификат в центре сертификации.</span><span class="sxs-lookup"><span data-stu-id="90e4b-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="90e4b-134">Вы должны заранее узнать, требуются ли имя пользователя и пароль для запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="90e4b-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="90e4b-135">У вашего администратора вашего ЦС есть нужная информация, и вам может потребоваться помощь в этом действии.</span><span class="sxs-lookup"><span data-stu-id="90e4b-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="90e4b-136">Если вам необходимо указать альтернативные сертификаты, установите флажок, укажите имя пользователя и пароль в текстовых полях и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="90e4b-137">На странице **Указание альтернативного шаблона сертификата** нажмите кнопку **Далее**, чтобы использовать шаблон веб-сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90e4b-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e4b-p110">Если ваша организация создала шаблон для использования в качестве альтернативы для шаблона веб-сервера по умолчанию, установите флажок, а затем введите имя альтернативного шаблона. Вам потребуется имя шаблона, заданное администратором центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="90e4b-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="90e4b-140">На странице **имя и параметры безопасности** укажите **понятное имя** , которое позволит вам определять сертификат и назначение.</span><span class="sxs-lookup"><span data-stu-id="90e4b-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="90e4b-141">Если оставить поле пустым, имя создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="90e4b-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="90e4b-142">Задайте значение **Длина в битах** для ключа или примите значение по умолчанию, равное 2048 битам.</span><span class="sxs-lookup"><span data-stu-id="90e4b-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="90e4b-143">Выберите **Пометить закрытый ключ сертификата как доступный для экспорта**, если вы определили, что сертификат и закрытый ключ потребуется перемещать или копировать в другие системы, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e4b-144">Lync Server 2013 имеет минимальные требования для экспортируемого закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="90e4b-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="90e4b-145">Одно из таких мест — пограничные серверы в пуле, где служба проверки подлинности при ретрансляции мультимедиа использует копии этого сертификата вместо отдельных сертификатов для каждого из экземпляров пула.</span><span class="sxs-lookup"><span data-stu-id="90e4b-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="90e4b-146">При необходимости укажите информацию об организации на странице **Сведения об организации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="90e4b-147">При необходимости укажите информацию о местоположении на странице **Сведения о местоположении** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="90e4b-148">На странице **Имя субъекта/альтернативные имена субъектов** просмотрите добавляемые альтернативные имена субъектов и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="90e4b-149">На странице **Настройка домена SIP** выберите **Домен SIP** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="90e4b-150">На странице **Настройка дополнительных альтернативных имен субъектов** добавьте все необходимые альтернативные имена субъектов, включая те из них, которые могут потребоваться в будущем для дополнительных доменов SIP, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="90e4b-p113">На странице **Сводка по запросу на сертификат** просмотрите сводные сведения. Если они верны, нажмите кнопку **Далее**. Если необходимо внести исправления, нажмите кнопку **Назад**, чтобы вернуться к нужной странице.</span><span class="sxs-lookup"><span data-stu-id="90e4b-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="90e4b-154">На странице **Выполнение команд** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="90e4b-155">On the **Online Certificate Request Status** page, review the information returned.</span><span class="sxs-lookup"><span data-stu-id="90e4b-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="90e4b-156">You should note that the certificate was issued and installed into the local certificate store.</span><span class="sxs-lookup"><span data-stu-id="90e4b-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="90e4b-157">Если сообщение о том, что оно было выпущено и установлено, недействительно, убедитесь, что корневой сертификат ЦС установлен в хранилище доверенных корневых ЦС сервера.</span><span class="sxs-lookup"><span data-stu-id="90e4b-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="90e4b-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span><span class="sxs-lookup"><span data-stu-id="90e4b-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="90e4b-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="90e4b-160">По умолчанию установлен флажок **назначения сертификата на использование сертификата сервера Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="90e4b-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="90e4b-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="90e4b-162">Если вы сняли флажок назначения сертификата **на использование сертификата сервера Lync Server** на предыдущей странице, появится страница **назначения сертификата** .</span><span class="sxs-lookup"><span data-stu-id="90e4b-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="90e4b-163">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-163">Click **Next**.</span></span>

18. <span data-ttu-id="90e4b-p116">На странице **Хранилище сертификатов** выберите запрошенный сертификат. Чтобы просмотреть сертификат, щелкните элемент **Просмотр сведений о сертификате**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e4b-166">Если на странице <STRONG>состояния запроса онлайнового сертификата</STRONG> обнаружена неполадка, связанная с сертификатом, например недействительный сертификат, Просмотр фактического сертификата поможет решить эту неполадку.</span><span class="sxs-lookup"><span data-stu-id="90e4b-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="90e4b-167">Недействительность сертификата может быть вызвана двумя причинами: указанное ранее отсутствие сертификата доверенного корневого центра сертификации, а также отсутствие закрытого ключа, сопоставленного с этим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="90e4b-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="90e4b-168">Сведения об устранении этих двух проблем см. в документации по центру сертификации.</span><span class="sxs-lookup"><span data-stu-id="90e4b-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="90e4b-169">На странице **Сводка по назначениям сертификатов** просмотрите представленные сведения, чтобы убедиться, что это именно тот сертификат, который требуется назначить, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="90e4b-p118">На странице **Выполнение команд** просмотрите выходные данные команды. Щелкните элемент **Просмотреть журнал**, если хотите ознакомиться с процессом назначения либо были выданы ошибка или предупреждение. После завершения просмотра нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="90e4b-173">На странице **мастера сертификатов** убедитесь, что для сертификата задано **состояние** "назначено", а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="90e4b-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90e4b-174">См. также</span><span class="sxs-lookup"><span data-stu-id="90e4b-174">See Also</span></span>


[<span data-ttu-id="90e4b-175">Требования инфраструктуры сертификатов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90e4b-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

