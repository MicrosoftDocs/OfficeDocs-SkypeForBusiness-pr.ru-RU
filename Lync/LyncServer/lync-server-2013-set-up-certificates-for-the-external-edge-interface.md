---
title: 'Lync Server 2013: Настройка сертификатов для внешнего интерфейса пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec2bad8f01e773d50f8d722ddbbf4be0757cb31d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="bfae0-102">Настройка сертификатов для внешнего пограничного интерфейса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfae0-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfae0-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bfae0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfae0-104">При запуске мастера сертификатов следует убедиться, что вход выполнен с использованием учетной записи, являющейся членом группы, которой назначены соответствующие разрешения для используемого шаблона сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="bfae0-105">По умолчанию запрос на сертификат сервера Lync Server будет использовать шаблон сертификата веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="bfae0-106">Если для запроса на сертификат, использующего этот шаблон, применяется учетная запись, которая является членом группы RTCUniversalServerAdmins, проверьте, назначены ли этой группе разрешения на регистрацию, необходимые для использования этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="bfae0-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="bfae0-107">Каждому пограничному серверу требуется общедоступный сертификат на интерфейс между сетью периметра и Интернетом, и альтернативное имя субъекта сертификата должно содержать внешние имена полных доменных имен пограничной службы доступа и пограничной службы веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="bfae0-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="bfae0-108">Сведения о данном и других требованиях к сертификатам приведены [в статье требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bfae0-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="bfae0-109">Список общедоступных центров сертификации (ЦС), предоставляющих сертификаты, которые соответствуют определенным требованиям для Объединенных сертификатов и партнерской корпорации Майкрософт, чтобы убедиться, что они работают с мастером сертификатов Lync Server 2013, можно узнать в статье базы знаний Майкрософт 929395, "Объединенные партнеры сертификатов для Exchange Server и Communications Server" в [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="bfae0-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="bfae0-110">Настройка сертификатов для внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="bfae0-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="bfae0-111">Чтобы настроить сертификат для внешнего пограничного интерфейса на сайте, с помощью процедур, приведенных в данном разделе, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bfae0-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="bfae0-112">Создайте запрос на сертификат для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="bfae0-113">Отправьте этот запрос в свой общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="bfae0-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="bfae0-114">Импортируйте сертификат для внешнего интерфейса каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="bfae0-115">Назначьте сертификат внешнему интерфейсу каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="bfae0-p102">Если в вашем развертывании имеется несколько пограничных серверов, экспортируйте сертификат вместе с его закрытым ключом, после чего скопируйте его на остальные пограничные серверы. Затем импортируйте и назначьте его для каждого пограничного сервера, как описано выше. Повторите эту процедуру для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="bfae0-p103">Общедоступные сертификаты можно запрашивать непосредственно в общедоступном центре сертификации (например, на веб-сайте общедоступного ЦС). В процедурах этого раздела для большинства задач с сертификатами используется мастер сертификатов. При запросе сертификата непосредственно в общедоступном ЦС придется соответствующим образом изменить каждую процедуру для запроса, транспортировки и импорта сертификата, а также для импорта цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="bfae0-p104">При запросе сертификата во внешнем ЦС предоставленные учетные данные должны иметь права на запрос сертификата из этого ЦС. Каждый ЦС имеет политику безопасности, определяющую, каким учетным данным (т.е. конкретным именам пользователей и групп) разрешается запрашивать, выдавать, читать сертификаты или управлять ими.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="bfae0-124">Если для импорта цепочки сертификатов и сертификата планируется использовать консоль управления (MMC) "Сертификаты", то необходимо импортировать их в хранилище сертификатов для компьютера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="bfae0-125">Если вы импортируете их в хранилище сертификатов пользователя или службы, сертификат будет недоступен для назначения в мастере сертификатов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bfae0-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="bfae0-126">Создание запроса на сертификат для внешнего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="bfae0-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="bfae0-127">На пограничном сервере в мастере развертывания нажмите кнопку **Run again (Запустить снова)** рядом с пунктом **Step 3: Request, Install, or Assign Certificates (Шаг 3. Запрос, установка или назначение сертификатов)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfae0-128">Если ваша организация хочет поддерживает подключение к общедоступным системам обмена мгновенными сообщениями с AOL, нельзя использовать мастер развертывания Lync Server для запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="bfae0-129">Вместо этого выполните действия из процедуры “Создание запроса на сертификат для внешнего интерфейса пограничного сервера для поддержки общедоступного подключения к системе обмена мгновенными сообщениями AOL”, которая приводится ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bfae0-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="bfae0-130">Если в одном расположении пула несколько пограничных серверов, можно запустить мастер сертификатов Lync Server 2013 на одном из пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="bfae0-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="bfae0-131">На странице **Available Certificate Tasks** (Доступные задачи сертификатов) щелкните команду **Create a new certificate request** (Создать новый запрос сертификата).</span><span class="sxs-lookup"><span data-stu-id="bfae0-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="bfae0-132">На странице **запроса сертификата** выберите пункт **External Edge Certificate** (Внешний сертификат пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="bfae0-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="bfae0-133">На странице **Отложенный или немедленный запрос** установите флажок **Подготовить запрос сейчас, чтобы отправить его позже**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="bfae0-134">На странице **файл запроса сертификата** введите полный путь и имя файла, в который будет сохранен запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="bfae0-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="bfae0-135">На странице **указания альтернативного шаблона сертификата** для использования шаблона, отличного от шаблона WebServer по умолчанию, установите флажок **Use alternative certificate template for the selected certification authority** (Использовать альтернативный шаблон сертификата для выбранного центра сертификации).</span><span class="sxs-lookup"><span data-stu-id="bfae0-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="bfae0-136">На странице **настроек имени и безопасности** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bfae0-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="bfae0-137">В поле **Friendly name (Понятное имя)** введите отображаемое имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="bfae0-138">В поле **Bit length (Длина в битах)** задайте длину в битах (обычно это установленное по умолчанию значение **2048**).</span><span class="sxs-lookup"><span data-stu-id="bfae0-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="bfae0-139">Убедитесь, что установлен флажок **Mark certificate private key as exportable (Пометить закрытый ключ сертификата как экспортируемый)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="bfae0-140">На странице **сведений об организации** укажите имя организации и подразделения (например, отделения или отдела).</span><span class="sxs-lookup"><span data-stu-id="bfae0-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="bfae0-141">На странице **сведений о местоположении** укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="bfae0-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="bfae0-p107">На странице **имени субъекта и альтернативных имен субъекта** отображаются сведения, автоматически заполненные мастером. Если требуются дополнительные альтернативные имена субъекта, то они указываются в следующих двух действиях.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="bfae0-144">На странице **Параметры домена SIP в альтернативных именах субъектов (SAN)** установите флажок домен, чтобы добавить SIP. \<sipdomain\> запись в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="bfae0-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="bfae0-145">На странице **Configure Additional Subject Alternate Names (Настройка дополнительных альтернативных имен субъекта)** укажите все нужные дополнительные альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="bfae0-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="bfae0-146">На странице **Request Summary (Сводка по запросу)** просмотрите сведения о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="bfae0-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="bfae0-147">После завершения выполнения команды выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bfae0-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="bfae0-148">Чтобы просмотреть журнал запроса на сертификат, нажмите **View Log (Просмотреть журнал)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="bfae0-149">Чтобы завершить запрос на сертификат, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="bfae0-150">На странице **Certificate Request File (Файл запроса сертификата)** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bfae0-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="bfae0-151">Чтобы просмотреть файл запроса подписи сертификата (CSR-файл), нажмите кнопку **View (Просмотр)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="bfae0-152">Чтобы закрыть мастер, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="bfae0-153">Скопируйте выходной файл в расположение, из которого можно будет отправить его в общедоступный ЦС.</span><span class="sxs-lookup"><span data-stu-id="bfae0-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="bfae0-154">Создание запроса на сертификат для внешнего интерфейса пограничного сервера для поддержки общедоступного подключения к системе обмена мгновенными сообщениями AOL</span><span class="sxs-lookup"><span data-stu-id="bfae0-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="bfae0-155">Если необходимый шаблон доступен для ЦС, используйте следующий командлет Windows PowerShell на пограничном сервере, чтобы запросить сертификат:</span><span class="sxs-lookup"><span data-stu-id="bfae0-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="bfae0-156">Имя сертификата по умолчанию для шаблона, указанного в Lync Server 2013, — Web Server.</span><span class="sxs-lookup"><span data-stu-id="bfae0-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="bfae0-157">Указывайте имя \<\> шаблона только в том случае, если требуется использовать шаблон, отличный от шаблона по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bfae0-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfae0-158">Если в Организации требуется поддерживать связь с общедоступной службой обмена мгновенными сообщениями с AOL, необходимо использовать Windows PowerShell вместо мастера сертификатов, чтобы запросить сертификат для внешнего края службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="bfae0-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="bfae0-159">Это связано с тем, что шаблон веб-сервера Lync Server 2013, который мастер сертификатов использует для запроса сертификата, не поддерживает настройку клиентского EKU.</span><span class="sxs-lookup"><span data-stu-id="bfae0-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="bfae0-160">Прежде чем использовать Windows PowerShell для создания сертификата, администратору ЦС необходимо создать и развернуть новый шаблон, поддерживающий клиентское EKU.</span><span class="sxs-lookup"><span data-stu-id="bfae0-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="bfae0-161">Отправка запроса в общедоступный центр сертификации</span><span class="sxs-lookup"><span data-stu-id="bfae0-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="bfae0-162">Откройте выходной файл.</span><span class="sxs-lookup"><span data-stu-id="bfae0-162">Open the output file.</span></span>

2.  <span data-ttu-id="bfae0-163">Скопируйте и вставьте содержимое запроса подписи сертификата (CSR-файла).</span><span class="sxs-lookup"><span data-stu-id="bfae0-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="bfae0-164">При запросе укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="bfae0-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="bfae0-165">**Microsoft** в качестве серверной платформы;</span><span class="sxs-lookup"><span data-stu-id="bfae0-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="bfae0-166">**IIS** в качестве версии;</span><span class="sxs-lookup"><span data-stu-id="bfae0-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="bfae0-167">**Web Server** в качестве типа использования;</span><span class="sxs-lookup"><span data-stu-id="bfae0-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="bfae0-168">**PKCS7** в качестве формата ответа.</span><span class="sxs-lookup"><span data-stu-id="bfae0-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="bfae0-169">Когда общедоступный ЦС проверит ваши сведения, вы получите сообщение электронной почты с текстом, необходимым для вашего сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="bfae0-170">Скопируйте текст из этого сообщения и сохраните его в текстовом файле (TXT-файле) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bfae0-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="bfae0-171">Импорт сертификата для внешнего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="bfae0-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="bfae0-172">Войдите как член группы администраторов на тот же пограничный сервер, на котором создавался запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="bfae0-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="bfae0-173">В мастере развертывания на странице **Deploy Edge Server (Развертывание пограничного сервера)** нажмите кнопку **Run again (Запустить снова)** рядом с пунктом **Step 3: Request, Install, or Assign Certificates (Шаг 3. Запрос, установка или назначение сертификатов)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="bfae0-174">На странице **Available Certificate Tasks (Доступные задачи с сертификатами)** нажмите **Import a certificate from a .p7b, pfx or .cer file (Импортировать сертификат из файла P7B, PFX или CER)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="bfae0-p110">На странице **Import Certificate (Импорт сертификата)** нажмите кнопку **Обзор**, чтобы найти и выбрать сертификат, запрошенный для внешнего интерфейса пограничного сервера (или можно ввести полный путь и имя). Если сертификат содержит закрытый ключ, выберите **Certificate file contains certificate’s private key (Файл сертификата, содержащий закрытый ключ сертификата)** и введите пароль для закрытого ключа. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="bfae0-178">На странице **Import Certificate Summary (Сводка по импорту сертификата)** просмотрите сводку и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="bfae0-179">На странице **Executing Commands (Выполненные команды)** просмотрите результаты импорта, при необходимости получения дополнительных сведений нажмите кнопку **View Log (Просмотреть журнал)**, а затем нажмите кнопку **Готово**, чтобы завершить импорт сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="bfae0-p111">Если настраивается пул пограничных серверов, экспортируйте сертификат с его закрытым ключом, как описывается в процедуре “Экспорт сертификата с закрытым ключом для пограничных серверов в пуле” далее в этом разделе. Скопируйте экспортированный файл сертификата на остальные пограничные сервера и импортируйте его в хранилище компьютера на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="bfae0-182">Экспорт сертификата с закрытым ключом для пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="bfae0-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="bfae0-183">Войдите как член группы администраторов на тот же пограничный сервер, на котором выполнялся импорт сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="bfae0-184">Нажмите кнопку **Пуск**, выберите пункт **Выполнить** и введите **MMC**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="bfae0-185">В консоли управления (MMC) последовательно выберите пункты **Файл** и **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="bfae0-186">В окне **Добавление и удаление оснасток** выберите пункт **Сертификаты** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="bfae0-187">В диалоговом окне **Сертификаты** выберите пункт **Учетная запись компьютера**, нажмите кнопку **Далее**, выберите пункт **Локальный компьютер (на котором запущена эта консоль)** в разделе **Выбор компьютера**, нажмите кнопку **Готово**, а затем нажмите кнопку **ОК**, чтобы завершить настройку консоли MMC.</span><span class="sxs-lookup"><span data-stu-id="bfae0-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="bfae0-188">Дважды щелкните пункт **Сертификаты (локальный компьютер)**, чтобы развернуть хранилища сертификатов, дважды щелкните пункт **Личные**, а затем дважды щелкните пункт **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bfae0-p112">Если в личном хранилище сертификатов для локального компьютера сертификаты отсутствуют, то отсутствует и закрытый ключ, связанный с импортированным сертификатом. Проанализируйте действия по отправке запроса и импорту. Если проблема сохраняется, обратитесь к своему администратору центра сертификации или к поставщику.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="bfae0-192">В **личном хранилище сертификатов для локального компьютера** щелкните правой кнопкой мыши экспортируемый сертификат, выберите пункт **Все задачи** и нажмите **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="bfae0-193">В мастере экспорта сертификатов нажмите кнопку **Далее**, установите флажок **Да, экспортировать закрытый ключ** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfae0-p113">Если установить флажок <STRONG>Да, экспортировать закрытый ключ</STRONG> невозможно, то закрытый ключ, связанный с этим сертификатом, не был помечен для экспорта. В этом случае придется запросить этот сертификат снова и проверить, что в сертификате отмечено разрешение экспорта закрытого ключа, после чего продолжить процедуру экспорта. Обратитесь к администратору центра сертификации или к поставщику.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="bfae0-197">В диалоговом окне Экспорт форматов файлов выберите файл **обмена личной информацией —\#PKCS 12 (. PFX)** , а затем выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="bfae0-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="bfae0-198">Включить по возможности все сертификаты в путь сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="bfae0-199">Экспортировать все расширенные свойства.</span><span class="sxs-lookup"><span data-stu-id="bfae0-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="bfae0-p114">При экспорте сертификата с пограничного сервера не устанавливайте флажок <STRONG>Удалить закрытый ключ после успешного экспорта</STRONG>. Установка этого флажка потребует выполнения импорта сертификата и закрытого ключа на данный пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="bfae0-202">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-202">Click **Next**.</span></span>

11. <span data-ttu-id="bfae0-203">Введите пароль для закрытого ключа, повторите его для подтверждения и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="bfae0-p115">Введите путь и имя файла для экспортированного сертификата, используя расширение PFX. Этот путь должен быть доступен для всех остальных пограничных серверов в пуле, или должна быть возможна транспортировка с помощью съемного носителя, например USB-устройства флэш-памяти. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="bfae0-207">Просмотрите сводку на странице **Завершение мастера экспорта сертификатов** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="bfae0-208">В диалоговом окне, сообщающем об успешном экспорте, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="bfae0-209">Импортируйте экспортированный файл сертификата на остальные пограничные серверы, выполнив действия, описанные в процедуре “Импорт сертификата для внешнего интерфейса пограничного сервера” в этом разделе выше.</span><span class="sxs-lookup"><span data-stu-id="bfae0-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="bfae0-210">Назначение сертификата внешнему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="bfae0-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="bfae0-211">На каждом пограничном сервере в мастере развертывания нажмите кнопку **Run again (Запустить снова)** рядом с пунктом **Step 3: Request, Install, or Assign Certificates (Шаг 3. Запрос, установка или назначение сертификатов)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="bfae0-212">На странице **Available Certificate Tasks (Доступные задачи с сертификатами)** выберите пункт **Assign an existing certificate (Назначить существующий сертификат)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="bfae0-213">На странице **Certificate Assignment (Назначение сертификата)** выберите пункт **External Edge Certificate (Внешний пограничный сертификат)** и установите флажок **Advanced Certificate Usages (Расширенное использование сертификата)**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="bfae0-214">На странице **Advanced Certificate Usages (Расширенное использование сертификата)** установите все флажки, чтобы назначить все варианты использования сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfae0-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="bfae0-215">На странице **Certificate Store (Хранилище сертификатов)** выберите общедоступный сертификат, который был запрошен и импортирован для внешнего интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfae0-216">Если запрошенный и импортированный сертификат отсутствует в списке, можно использовать один из способов устранения неполадки, заключающийся в том, чтобы проверить соответствие имени субъекта и альтернативных имен субъектов всем требованиям для сертификата, и в случае, если сертификат и цепочка сертификатов импортировались вручную, а не с помощью предыдущих процедур, проверить, что сертификат находится в правильном хранилище сертификатов (в хранилище сертификатов компьютера, а не пользователя или службы).</span><span class="sxs-lookup"><span data-stu-id="bfae0-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="bfae0-217">На странице **Certificate Assignment Summary (Сводка по назначениям сертификатов)** просмотрите все параметры, а затем нажмите кнопку **Далее**, чтобы назначить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="bfae0-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="bfae0-218">На странице завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bfae0-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="bfae0-219">После использования этой процедуры для назначения пограничного сертификата откройте оснастку "Сертификаты" на каждом сервере, разверните узел **Сертификаты (локальный компьютер)**, разверните узел **Личные**, выберите пункт **Сертификаты** и проверьте, значится ли этот сертификат в области сведений.</span><span class="sxs-lookup"><span data-stu-id="bfae0-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="bfae0-220">Если в развертывании имеется несколько пограничных серверов, повторите эту процедуру для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bfae0-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

