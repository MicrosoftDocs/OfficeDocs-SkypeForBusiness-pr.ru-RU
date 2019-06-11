---
title: 'Lync Server 2013: настройка сертификатов для внешнего интерфейса пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="77439-102">Настройка сертификатов для внешнего интерфейса пограничного сервера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77439-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77439-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="77439-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77439-104">При запуске мастера сертификатов убедитесь, что вы вошли в систему под учетной записью, которая является членом группы, которой назначены соответствующие разрешения для типа шаблона сертификата, который вы будете использовать.</span><span class="sxs-lookup"><span data-stu-id="77439-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="77439-105">По умолчанию запрос сертификата сервера Lync будет использовать шаблон сертификата веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="77439-106">Если вы используете учетную запись, которая входит в группу Рткуниверсалсерверадминс, чтобы запросить сертификат с помощью этого шаблона, убедитесь, что группе назначены разрешения, необходимые для использования этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="77439-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="77439-107">Каждый пограничный сервер требует наличия общедоступного сертификата на интерфейсе между демилитаризованной зоной и Интернетом, а альтернативное имя субъекта сертификата должно содержать внешние имена службы пограничного доступа и службы Edge для веб-конференций. полные доменные имена (FQDN).</span><span class="sxs-lookup"><span data-stu-id="77439-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="77439-108">Подробнее об этих и других требованиях к сертификатам можно узнать в статьях [требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="77439-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="77439-109">Список общедоступных центров сертификации (ЦС), предоставляющих сертификаты, соответствующие определенным требованиям для Объединенных сертификатов и связанных с корпорацией Майкрософт, чтобы убедиться, что они работают с мастером создания сертификата Lync Server 2013, ознакомьтесь со статьей Статья 929395 базы знаний Майкрософт "партнеры по сертификатам единой системы связи для Exchange Server и Communications Server" в [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="77439-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="77439-110">Настройка сертификатов во внешних интерфейсах</span><span class="sxs-lookup"><span data-stu-id="77439-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="77439-111">Чтобы настроить сертификат на внешнем интерфейсе EDGE на сайте, выполните указанные ниже действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="77439-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="77439-112">Создайте запрос сертификата для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="77439-113">Отправьте запрос в общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="77439-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="77439-114">Импортируйте сертификат для внешнего интерфейса каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="77439-115">Назначьте сертификат внешнему интерфейсу каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="77439-116">Если в развертывании есть несколько пограничных серверов, экспортируйте сертификат вместе с закрытым ключом, а затем скопируйте его на другие пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="77439-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="77439-117">Затем для каждого пограничного сервера импортируйте его и назначьте его описанным ранее образом.</span><span class="sxs-lookup"><span data-stu-id="77439-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="77439-118">Повторите эти действия для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="77439-119">Вы можете запросить общедоступные сертификаты прямо в общедоступном центре сертификации (ЦС) (например, на веб-сайте общедоступного ЦС).</span><span class="sxs-lookup"><span data-stu-id="77439-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="77439-120">В этой статье описано использование мастера сертификатов для большинства задач с сертификатами.</span><span class="sxs-lookup"><span data-stu-id="77439-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="77439-121">Если вы решили запросить сертификат прямо из общедоступного центра сертификации, вам потребуется изменить каждую из них, чтобы выполнить запрос, транспортировку и импортировать сертификат, а также импортировать цепочку сертификатов.</span><span class="sxs-lookup"><span data-stu-id="77439-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="77439-122">При запросе сертификата из внешнего ЦС предоставленные учетные данные должны иметь права на запрос сертификата от этого ЦС.</span><span class="sxs-lookup"><span data-stu-id="77439-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="77439-123">У каждого ЦС есть политика безопасности, определяющая, какие учетные записи (то есть конкретные имена пользователей и групп) разрешено запрашивать, выдать, управлять или читать сертификаты.</span><span class="sxs-lookup"><span data-stu-id="77439-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="77439-124">Если вы решили использовать консоль управления Microsoft Management Console (MMC) для импорта цепочки сертификатов и сертификата, нужно импортировать их в хранилище сертификатов для компьютера.</span><span class="sxs-lookup"><span data-stu-id="77439-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="77439-125">Если вы импортируете их в хранилище сертификатов пользователей или служб, сертификат будет недоступен для назначения в мастере создания сертификата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77439-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="77439-126">Создание запроса на сертификат для внешнего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="77439-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="77439-127">На пограничном сервере в мастере развертывания рядом с **шагом 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="77439-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77439-128">Если ваша организация хочет поддерживать связь с Интернетом через AOL, вы не можете запросить сертификат с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77439-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="77439-129">Вместо этого выполните действия, описанные в разделе "Создание запроса на сертификат для внешнего интерфейса пограничного сервера, чтобы обеспечить поддержку общедоступной службы обмена мгновенными сообщениями с AOL" в этой статье ниже.</span><span class="sxs-lookup"><span data-stu-id="77439-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="77439-130">Если в одном месте пула есть несколько пограничных серверов, вы можете запустить мастер сертификатов Lync Server 2013 на любом из серверов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="77439-131">На странице **Доступные задачи сертификатов** щелкните команду **Создать новый запрос сертификата**.</span><span class="sxs-lookup"><span data-stu-id="77439-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="77439-132">На странице **запроса сертификата** выберите **внешний Граничный сертификат**.</span><span class="sxs-lookup"><span data-stu-id="77439-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="77439-133">На странице **отложенный или немедленный запрос** установите флажок **подготовить запрос сейчас, но отправить позже** .</span><span class="sxs-lookup"><span data-stu-id="77439-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="77439-134">На странице " **файл запроса сертификата** " введите полный путь и имя файла, в который нужно сохранить запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="77439-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="77439-135">На странице " **Укажите другой шаблон сертификата** ", чтобы использовать шаблон, отличный от шаблона веб-сервера по умолчанию, установите флажок **использовать альтернативный шаблон сертификата для выбранного центра сертификации** .</span><span class="sxs-lookup"><span data-stu-id="77439-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="77439-136">На странице **имя и параметры безопасности** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77439-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="77439-137">В поле **понятное имя**введите отображаемое имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="77439-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="77439-138">В качестве **битовой длины**укажите длину в битах (обычно это значение по умолчанию — **2048**).</span><span class="sxs-lookup"><span data-stu-id="77439-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="77439-139">Убедитесь, что установлен флажок " **помечать закрытый ключ сертификата как экспортируемый** ".</span><span class="sxs-lookup"><span data-stu-id="77439-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="77439-140">На странице " **сведения об организации** " введите имя Организации и организационное подразделение (например, "подразделение" или "Отдел").</span><span class="sxs-lookup"><span data-stu-id="77439-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="77439-141">На странице **сведения о географическом** расположении укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="77439-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="77439-142">На странице **имя субъекта/альтернативная тема** отображается информация, которая будет автоматически заполнена мастером.</span><span class="sxs-lookup"><span data-stu-id="77439-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="77439-143">Если требуются дополнительные альтернативные имена субъектов, их можно указать в следующих двух шагах.</span><span class="sxs-lookup"><span data-stu-id="77439-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="77439-144">В **параметрах домена SIP на странице "альтернативные имена тем" (SAN)** установите флажок домен, чтобы добавить SIP. \<сипдомаин\> элемент в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="77439-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="77439-145">На странице **Настройка дополнительных имен для других тем** укажите необходимые дополнительные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="77439-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="77439-146">На странице **сводки запроса** ознакомьтесь со сведениями о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="77439-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="77439-147">После завершения выполнения команд выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77439-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="77439-148">Чтобы просмотреть журнал для запроса сертификата, нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="77439-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="77439-149">Чтобы завершить запрос сертификата, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="77439-150">На странице " **файл запроса сертификата** " выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77439-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="77439-151">Чтобы просмотреть созданный файл запроса подписи сертификата (CSR), нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="77439-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="77439-152">Для завершения работы мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="77439-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="77439-153">Скопируйте выходной файл в то место, где вы можете отправить его в общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="77439-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="77439-154">Создание запроса на сертификат для внешнего интерфейса пограничного сервера, чтобы обеспечить поддержку общедоступной службы обмена мгновенными сообщениями с AOL</span><span class="sxs-lookup"><span data-stu-id="77439-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="77439-155">Если необходимый шаблон доступен для центра сертификации, для запроса сертификата используйте следующий командлет Windows PowerShell на пограничном сервере:</span><span class="sxs-lookup"><span data-stu-id="77439-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="77439-156">Имя сертификата по умолчанию для шаблона, указанного в Lync Server 2013, — это веб-сервер.</span><span class="sxs-lookup"><span data-stu-id="77439-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="77439-157">Указывайте имя \<\> шаблона только в том случае, если вам нужно использовать шаблон, отличный от шаблона по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77439-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77439-158">Если в вашей организации требуется поддержка общедоступной службы обмена мгновенными сообщениями с AOL, вы должны использовать Windows PowerShell вместо мастера сертификатов, чтобы запросить назначение сертификата внешнему краю службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="77439-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="77439-159">Это происходит из-за того, что шаблон сервера Lync Server 2013, используемый мастером сертификатов для запроса сертификата, не поддерживает конфигурацию EKU клиентов.</span><span class="sxs-lookup"><span data-stu-id="77439-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="77439-160">Прежде чем использовать Windows PowerShell для создания сертификата, администратор центра администрирования должен создать и развернуть новый шаблон, поддерживающий клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="77439-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="77439-161">Отправка запроса в общедоступный центр сертификации</span><span class="sxs-lookup"><span data-stu-id="77439-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="77439-162">Откройте выходной файл.</span><span class="sxs-lookup"><span data-stu-id="77439-162">Open the output file.</span></span>

2.  <span data-ttu-id="77439-163">Скопируйте и вставьте содержимое запроса подписи сертификата (CSR).</span><span class="sxs-lookup"><span data-stu-id="77439-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="77439-164">При появлении запроса укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="77439-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="77439-165">**Microsoft** является серверной платформой.</span><span class="sxs-lookup"><span data-stu-id="77439-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="77439-166">Версия **служб IIS** .</span><span class="sxs-lookup"><span data-stu-id="77439-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="77439-167">**Веб-сервер** в качестве типа использования.</span><span class="sxs-lookup"><span data-stu-id="77439-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="77439-168">**PKCS7** в качестве формата ответа.</span><span class="sxs-lookup"><span data-stu-id="77439-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="77439-169">Когда общедоступный центр сертификации проверит ваши данные, вы получите сообщение электронной почты, содержащее текст, необходимый для вашего сертификата.</span><span class="sxs-lookup"><span data-stu-id="77439-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="77439-170">Скопируйте текст из сообщения электронной почты и сохраните его в текстовом файле (txt) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="77439-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="77439-171">Импорт сертификата для внешнего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="77439-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="77439-172">Войдите в систему как участник группы Администраторы на тот же самый граничный сервер, на котором был создан запрос сертификата.</span><span class="sxs-lookup"><span data-stu-id="77439-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="77439-173">В мастере развертывания на странице **Развертывание пограничного сервера** в разделе **Этап 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="77439-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="77439-174">На странице **Доступные задачи для сертификатов** щелкните **Импорт сертификата из файла. p7b, PFX или CER**.</span><span class="sxs-lookup"><span data-stu-id="77439-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="77439-175">На странице **Импорт сертификата** нажмите кнопку **Обзор** , чтобы найти и выбрать сертификат, запрошенный внешним интерфейсом пограничного сервера (или введите полный путь и имя файла).</span><span class="sxs-lookup"><span data-stu-id="77439-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="77439-176">Если сертификат состоит из закрытого ключа, выберите **файл сертификата, который включает закрытый ключ сертификата** , и введите пароль для закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="77439-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="77439-177">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-177">Click **Next**.</span></span>

5.  <span data-ttu-id="77439-178">На странице **Сводка импорта сертификата** просмотрите сводку и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="77439-179">На странице **выполнение команд**просмотрите результаты импорта, нажмите кнопку **Просмотреть журнал** , чтобы получить дополнительные сведения, а затем нажмите кнопку **Готово** , чтобы завершить импорт сертификата.</span><span class="sxs-lookup"><span data-stu-id="77439-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="77439-180">Если вы настраиваете пул пограничного сервера, экспортируйте сертификат с его закрытым ключом, как описано в разделе "чтобы экспортировать сертификат с закрытым ключом для пограничных серверов в пуле" Далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="77439-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="77439-181">Скопируйте экспортированный файл сертификата на другие пограничные серверы и импортируйте его в хранилище компьютера на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="77439-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="77439-182">Экспорт сертификата с закрытым ключом для пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="77439-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="77439-183">Войдите в систему как участник группы Администраторы на тот же самый граничный сервер, на котором вы импортировали сертификат.</span><span class="sxs-lookup"><span data-stu-id="77439-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="77439-184">Нажмите кнопку **Пуск**и выберите пункт **выполнить**, а затем — команду **MMC**.</span><span class="sxs-lookup"><span data-stu-id="77439-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="77439-185">В консоли управления (MMC) откройте вкладку **файл**и выберите команду **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="77439-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="77439-186">В окне " **Добавление и удаление оснасток**" выберите " **Сертификаты**" и нажмите кнопку " **добавить**".</span><span class="sxs-lookup"><span data-stu-id="77439-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="77439-187">В диалоговом окне **Сертификаты** выберите **учетная запись компьютера**, нажмите кнопку **Далее**, выберите пункт **локальный компьютер: (компьютер, на котором запущена эта консоль)** на вкладке на **компьютере**нажмите кнопку **Готово** , а затем — **ОК** . Завершите настройку консоли MMC.</span><span class="sxs-lookup"><span data-stu-id="77439-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="77439-188">Дважды щелкните элемент **Сертификаты (локальный компьютер)** , чтобы развернуть хранилище сертификатов, дважды щелкните **личное**и дважды щелкните **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="77439-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77439-189">Если в личном хранилище сертификатов локального компьютера нет сертификатов, закрытый ключ, связанный с сертификатом, который был импортирован, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="77439-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="77439-190">Просматривайте шаги запроса и импорта.</span><span class="sxs-lookup"><span data-stu-id="77439-190">Review the request and import steps.</span></span> <span data-ttu-id="77439-191">Если проблема сохранится, обратитесь к администратору или поставщику центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="77439-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="77439-192">В **личном хранилище сертификатов локального компьютера**щелкните правой кнопкой мыши сертификат, который вы хотите экспортировать, выберите пункт **все задачи**, а затем нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="77439-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="77439-193">В мастере экспорта сертификатов нажмите кнопку **Далее**, выберите **Да, экспорт закрытого ключа**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77439-194">Если выделение <STRONG>Да, экспорт закрытого ключа</STRONG> недоступен, закрытый ключ, связанный с этим сертификатом, не был помечен для экспорта.</span><span class="sxs-lookup"><span data-stu-id="77439-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="77439-195">Вам потребуется еще раз запросить сертификат, убедившись в том, что сертификат помечен для экспорта закрытого ключа, прежде чем можно будет продолжить экспорт.</span><span class="sxs-lookup"><span data-stu-id="77439-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="77439-196">Обратитесь к своему администратору или поставщику центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="77439-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="77439-197">В диалоговом окне Экспорт форматов файлов выберите пункт **Exchange для персональных данных\#— PKCS 12 (. PFX)** и выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="77439-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="77439-198">Включите по возможности все сертификаты в путь сертификации.</span><span class="sxs-lookup"><span data-stu-id="77439-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="77439-199">Экспорт всех расширенных свойств</span><span class="sxs-lookup"><span data-stu-id="77439-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="77439-200">При экспорте сертификата с пограничного сервера не выбирайте параметр <STRONG>Удаление закрытого ключа при успешном завершении экспорта</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="77439-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="77439-201">При выборе этого параметра потребуется импортировать сертификат и закрытый ключ на этот граничный сервер.</span><span class="sxs-lookup"><span data-stu-id="77439-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="77439-202">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-202">Click **Next**.</span></span>

11. <span data-ttu-id="77439-203">Введите пароль для закрытого ключа, введите его еще раз для подтверждения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="77439-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span><span class="sxs-lookup"><span data-stu-id="77439-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="77439-205">Путь должен быть доступен для всех других пограничных серверов в пуле или доступен для транспортировки с помощью съемных носителей (например, USB-устройства флэш-памяти).</span><span class="sxs-lookup"><span data-stu-id="77439-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="77439-206">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77439-206">Click **Next**.</span></span>

13. <span data-ttu-id="77439-207">Просмотрите сводные данные по **завершении работы мастера экспорта сертификатов**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="77439-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="77439-208">В диалоговом окне успешный экспорт нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="77439-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="77439-209">Импортируйте экспортированный файл сертификата на другие пограничные серверы, выполнив действия, описанные в разделе "Импорт сертификата для внешнего интерфейса пограничного сервера" ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="77439-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="77439-210">Назначение сертификата внешнему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="77439-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="77439-211">На каждом пограничном сервере в мастере развертывания рядом с **шагом 3: запрос, установка и назначение сертификатов**нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="77439-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="77439-212">На странице **Доступные задачи для сертификатов** выберите команду **назначить существующий сертификат**.</span><span class="sxs-lookup"><span data-stu-id="77439-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="77439-213">На странице " **назначение сертификата** " выберите " **внешний край** и флажок" **Дополнительно "использование сертификатов** ".</span><span class="sxs-lookup"><span data-stu-id="77439-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="77439-214">На странице **Дополнительные сведения об использовании сертификатов** установите флажок все флажки, чтобы назначить сертификат для всех использований.</span><span class="sxs-lookup"><span data-stu-id="77439-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="77439-215">На странице **хранилище сертификатов** выберите общедоступный сертификат, который вы просили и импортировали для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77439-216">Если запрошенный и импортированный сертификат отсутствует в списке, одним из способов их поддела является проверка того, что имя субъекта и название темы сертификата соответствуют всем требованиям для сертификата, и, если вы вручную импортировали сертификат и цепочка сертификатов вместо использования описанных выше процедур, сертификат находится в нужном хранилище сертификатов (хранилище сертификатов компьютера, а не в хранилище сертификатов пользователей или служб).</span><span class="sxs-lookup"><span data-stu-id="77439-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="77439-217">На странице **Сводка назначения сертификата** проверьте параметры и нажмите кнопку **Далее** , чтобы назначить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="77439-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="77439-218">На странице завершения работы мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="77439-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="77439-219">После использования этой процедуры для назначения граничного сертификата откройте оснастку сертификат на каждом сервере, разверните раздел **Сертификаты (локальный компьютер)**, а затем — **Личные**, выберите пункт **Сертификаты**и проверьте в области сведений, что сертификат указан.</span><span class="sxs-lookup"><span data-stu-id="77439-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="77439-220">Если в развертывании есть несколько пограничных серверов, повторите эти действия для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="77439-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

