---
title: Запрос и Настройка сертификата для обратного HTTP-прокси
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="48a2d-102">Запрос и Настройка сертификата для обратного HTTP-прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48a2d-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48a2d-103">_**Последнее изменение темы:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="48a2d-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="48a2d-104">Необходимо установить сертификат корневого центра сертификации (CA) на сервере под управлением Microsoft Forefront Threat Management Gateway 2010 или IIS ARR для инфраструктуры ЦС, которая выдала сертификаты сервера внутренним серверам, на которых работает Microsoft Lync. Сервер 2013.</span><span class="sxs-lookup"><span data-stu-id="48a2d-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="48a2d-p101">Вам также следует установить общий сертификат веб-сервера  на обратный прокси-сервер. Альтернативные имена субъектов этого сертификата  должны содержать опубликованные внешние полные доменные имена для каждого пула, в котором размещаются пользователи с включенной поддержкой удаленного доступа, а также внешние полные доменные имена всех Директоров или пулов Директоров, которые будут использоваться в рамках пограничной инфраструктуры. Альтернативное имя субъекта также должно содержать простой URL-адрес собрания, простой URL-адрес для телефонного подключения и — если вы развертываете мобильные приложения и планируете использовать автоматическое обнаружение — внешний URL-адрес службы автообнаружения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="48a2d-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="48a2d-108">Значение</span><span class="sxs-lookup"><span data-stu-id="48a2d-108">Value</span></span></th>
<th><span data-ttu-id="48a2d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="48a2d-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48a2d-110">Имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-111">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="48a2d-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="48a2d-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a2d-113">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-114">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="48a2d-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="48a2d-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="48a2d-116">Это имя субъекта также должно присутствовать в альтернативном имени субъекта.</span><span class="sxs-lookup"><span data-stu-id="48a2d-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a2d-117">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-118">Необязательные веб-службы директора (если директор развернута)</span><span class="sxs-lookup"><span data-stu-id="48a2d-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="48a2d-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a2d-120">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-121">Простой URL-адрес собрания</span><span class="sxs-lookup"><span data-stu-id="48a2d-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="48a2d-p102">Все простые URL-адреса собраний должны находиться в альтернативном имени субъекта. Каждый SIP-домен должен иметь хотя бы один активный простой URL-адрес собрания.</span><span class="sxs-lookup"><span data-stu-id="48a2d-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="48a2d-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a2d-125">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-126">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="48a2d-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="48a2d-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a2d-128">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-129">Сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="48a2d-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="48a2d-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a2d-131">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="48a2d-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="48a2d-132">Внешний URL-адрес службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="48a2d-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="48a2d-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48a2d-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="48a2d-134">Если вы также используете Microsoft Exchange Server, вам также потребуется настроить правила обратного прокси-сервера для URL-адресов автообнаружения Exchange и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="48a2d-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="48a2d-135">Если ваше внутреннее развертывание состоит из нескольких серверов Standard Edition или интерфейсных пулов, вам следует настроить правила веб-публикации для каждого полного доменного имени внешней веб-фермы и потребуется использовать сертификат и веб-прослушиватель для каждого из них либо получить сертификат, альтернативное имя субъекта которого содержит имена, используемые всеми пулами, назначить его веб-прослушивателю и совместно использовать в нескольких правилах веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="48a2d-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="48a2d-136">Создание запроса на сертификат</span><span class="sxs-lookup"><span data-stu-id="48a2d-136">Create a Certificate Request</span></span>

<span data-ttu-id="48a2d-137">Вы создаете запрос на сертификат на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="48a2d-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="48a2d-138">Вы создаете запрос на другом компьютере, но должен экспортировать подписанный сертификат с закрытым ключом и импортировать его на обратный прокси-сервер после того, как вы получили его от общедоступного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="48a2d-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="48a2d-139">Запрос на сертификат или запрос подписи сертификата (CSR) является запросом доверенного общедоступного центра сертификации (CA), который проверяет и подписывает открытый ключ запрашивающего компьютера.</span><span class="sxs-lookup"><span data-stu-id="48a2d-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="48a2d-140">При создании сертификата создается открытый ключ и закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="48a2d-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="48a2d-141">Только открытый ключ является общим и подписанным.</span><span class="sxs-lookup"><span data-stu-id="48a2d-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="48a2d-142">Как следует из названия, Открытый ключ предоставляется любому общедоступному запросу.</span><span class="sxs-lookup"><span data-stu-id="48a2d-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="48a2d-143">Открытый ключ предназначен для использования клиентами, серверами и другими запрашивающими стороны, которые требуют безопасного обмена данными и проверки удостоверения компьютера.</span><span class="sxs-lookup"><span data-stu-id="48a2d-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="48a2d-144">Закрытый ключ защищен и используется только компьютером, на котором создана эта комбинация ключей для расшифровки сообщений, зашифрованных с помощью открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="48a2d-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="48a2d-145">Закрытый ключ можно использовать для других целей.</span><span class="sxs-lookup"><span data-stu-id="48a2d-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="48a2d-146">Для обратного прокси-сервера использование шифрования данных является основным.</span><span class="sxs-lookup"><span data-stu-id="48a2d-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="48a2d-147">Секондарили проверка подлинности на основе сертификата на уровне ключа сертификата является другой, и она ограничена только проверкой того, что у запрашивающего пользователя есть открытый ключ компьютера, или что компьютер, на котором есть открытый ключ, фактически является компьютером, на котором он находится.</span><span class="sxs-lookup"><span data-stu-id="48a2d-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="48a2d-148">Если вы планируете одновременное планирование сертификатов пограничного сервера и сертификатов обратного прокси-сервера, обратите внимание на то, что существует много сходства между двумя требованиями к сертификатам.</span><span class="sxs-lookup"><span data-stu-id="48a2d-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="48a2d-149">Когда вы настраиваете и запрашиваете сертификат пограничного сервера, объедините пограничный сервер и альтернативные имена субъектов обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="48a2d-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="48a2d-150">Вы можете использовать один и тот же сертификат для обратного прокси-сервера, если вы экспортируете сертификат и закрытый ключ и копируете экспортированный файл в обратный прокси-сервер, а затем импортируете сертификат/ключ и назначаете его в соответствии с предстоящими процедурами.</span><span class="sxs-lookup"><span data-stu-id="48a2d-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="48a2d-151">Обратитесь к разделу требования к сертификатам для&nbsp;плана пограничного сервера<A href="lync-server-2013-plan-for-edge-server-certificates.md">для сертификатов пограничного сервера в Lync Server 2013</A> и обратной связи по сертификатам обратного прокси <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-сервера в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48a2d-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="48a2d-152">Убедитесь, что вы создаете сертификат с экспортируемым закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="48a2d-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="48a2d-153">Для пограничных серверов poold требуется создать сертификат и запрос сертификата с экспортируемым закрытым ключом, поэтому в мастере установки Lync Server для пограничного сервера можно установить флаг <STRONG>сделать закрытые ключи экспортируемым</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="48a2d-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="48a2d-154">После получения запроса на сертификат из общедоступного центра сертификации вы экспортируете сертификат и закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="48a2d-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="48a2d-155">В разделе "Экспорт сертификата с закрытым ключом для пограничных серверов в пуле" в разделе <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Настройка сертификатов для внешнего пограничного интерфейса для Lync Server 2013</A> для получения сведений о создании и экспорте сертификата с закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="48a2d-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="48a2d-156">Расширение сертификата должно иметь тип <STRONG>PFX</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="48a2d-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="48a2d-157">Чтобы создать запрос на подпись сертификата на компьютере, на котором будет назначен сертификат и закрытый ключ, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="48a2d-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="48a2d-158">**Создание запроса подписи сертификата**</span><span class="sxs-lookup"><span data-stu-id="48a2d-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="48a2d-159">Откройте консоль управления (MMC) и добавьте оснастку "сертификаты" и выберите **Компьютеры**, а затем — **Личные**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="48a2d-160">Сведения о том, как создать консоль сертификатов в консоли управления (MMC), можно найти [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)в статье.</span><span class="sxs-lookup"><span data-stu-id="48a2d-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="48a2d-161">Щелкните правой кнопкой мыши пункт **Сертификаты**, выберите **все задачи**, а затем **Дополнительные операции**, щелкните **создать настраиваемый запрос**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="48a2d-162">На странице " **регистрация сертификата** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="48a2d-163">На странице " **Выбор политики регистрации сертификатов** " в разделе **настраиваемый запрос**выберите пункт **Продолжить без политики регистрации**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="48a2d-164">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-164">Click **Next**.</span></span>

5.  <span data-ttu-id="48a2d-165">На странице **настраиваемый запрос** для **шаблона** выберите **устаревший ключ (без шаблона)**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="48a2d-166">Если поставщик сертификата не управляется каким бы то ни было иным способом, не устанавливайте флажок **Отключить расширения по умолчанию** и выберите **Формат запроса** на **PKCS \#10**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="48a2d-167">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-167">Click **Next**.</span></span>

6.  <span data-ttu-id="48a2d-168">На странице **сведения о сертификате** нажмите кнопку **сведения**, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="48a2d-169">На странице **свойств сертификата** на вкладке **Общие** в поле **понятное имя** введите имя этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="48a2d-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="48a2d-170">При необходимости введите описание в поле **Описание** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="48a2d-171">Понятное имя и описание обычно используются администратором для определения назначения сертификата, например **обратного прокси-прослушивателя для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="48a2d-172">Перейдите на вкладку **Тема** . В разделе **имя субъекта** для **типа**выберите **Общее имя** для типа имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="48a2d-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="48a2d-173">В поле **значение**введите имя субъекта, которое будет использоваться для обратного прокси-сервера, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="48a2d-174">В примере, приведенном в таблице в этом разделе, имя субъекта — webext.contoso.com, и оно будет вводиться в поле Value (значение) для имени субъекта.</span><span class="sxs-lookup"><span data-stu-id="48a2d-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="48a2d-175">На вкладке **Тема** в разделе **альтернативное имя**выберите **DNS** в раскрывающемся списке **тип**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="48a2d-176">Для каждого определенного альтернативного имени субъекта, которое требуется для сертификата, введите полное доменное имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="48a2d-177">Например, в таблице существует три альтернативных имени субъекта, meet.contoso.com, dialin.contoso.com и lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="48a2d-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="48a2d-178">В поле **значение** введите Meet.contoso.com, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="48a2d-179">Повторите эти действия для всех альтернативных имен субъектов, которые необходимо определить.</span><span class="sxs-lookup"><span data-stu-id="48a2d-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="48a2d-180">На странице **свойств сертификата** откройте вкладку **расширения** . На этой странице определяются криптографические ключи в **использовании ключа** и расширенное использование ключа в **расширенном использовании ключа (политики приложений)**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="48a2d-181">Щелкните стрелку **использования ключа** , чтобы показать **Доступные параметры**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="48a2d-182">В разделе Доступные параметры выберите пункт **Цифровая подпись**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="48a2d-183">Щелкните **Шифрование ключей**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="48a2d-184">Если флажок **сделать критическими критические применения ключей** не установлен, установите флажок.</span><span class="sxs-lookup"><span data-stu-id="48a2d-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="48a2d-185">Щелкните стрелку **расширенного использования ключа (политики приложений)** , чтобы показать **Доступные параметры**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="48a2d-186">В разделе Доступные параметры выберите **Проверка подлинности сервера**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="48a2d-187">Выберите **Проверка подлинности клиента**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="48a2d-188">Если установлен флажок **сделать критическим использование расширенных ключей** , снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="48a2d-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="48a2d-189">В отличие от флажка использование ключа (необходимо проверить) необходимо убедиться в том, что флажок расширенного ключа использования не установлен.</span><span class="sxs-lookup"><span data-stu-id="48a2d-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="48a2d-190">На странице " **Свойства сертификата** " откройте вкладку **закрытый ключ** . Щелкните стрелку **Параметры ключа** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="48a2d-191">В раскрывающемся списке **Размер ключа**выберите **2048** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="48a2d-192">Если вы создаете эту комбинацию ключей и CSR на компьютере, отличном от обратного прокси-сервера, для которого предназначен этот сертификат, выберите **сделать закрытым ключ экспортируемым**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="48a2d-194">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="48a2d-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="48a2d-195">Выбор варианта <strong>сделать экспорт закрытого ключа</strong> рекомендуется, если в ферме есть несколько обратных прокси-серверов, так как сертификат и закрытый ключ будут скопированы на каждый компьютер в ферме.</span><span class="sxs-lookup"><span data-stu-id="48a2d-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="48a2d-196">Если вы разрешите экспортируемый закрытый ключ, необходимо уделять особое внимание сертификату и компьютеру, на котором он создается.</span><span class="sxs-lookup"><span data-stu-id="48a2d-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="48a2d-197">Закрытый ключ, если он скомпрометирован, будет отображать сертификат бесполезен, а потенциально предоставлять компьютеру или компьютерам доступ к внешним и другим уязвимостям системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="48a2d-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="48a2d-198">На вкладке **закрытый ключ** щелкните стрелку **тип ключа** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="48a2d-199">Выберите параметр **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="48a2d-200">Нажмите кнопку **ОК** , чтобы сохранить заданные **Свойства сертификата** .</span><span class="sxs-lookup"><span data-stu-id="48a2d-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="48a2d-201">На странице " **регистрация сертификата** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="48a2d-202">На странице **где вы хотите сохранить автономный запрос?** вам будет предложено указать **имя файла** и **Формат файла** для сохранения запроса подписи сертификата.</span><span class="sxs-lookup"><span data-stu-id="48a2d-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="48a2d-203">В поле **имя файла** введите путь и имя файла запроса или нажмите кнопку **Обзор** , чтобы выбрать расположение файла, и введите имя файла для запроса.</span><span class="sxs-lookup"><span data-stu-id="48a2d-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="48a2d-204">В качестве **формата файла**выберите **базовый 64** или **двоичный**.</span><span class="sxs-lookup"><span data-stu-id="48a2d-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="48a2d-205">Выберите **Base 64** , если вы не указали иное у поставщика сертификатов.</span><span class="sxs-lookup"><span data-stu-id="48a2d-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="48a2d-206">Откройте файл запроса, сохраненный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="48a2d-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="48a2d-207">Отправляйте в свой общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="48a2d-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="48a2d-208">Корпорация Майкрософт выявила общедоступные ЦС, соответствующие требованиям для объединенных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="48a2d-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="48a2d-209">Список хранится в следующей статье базы знаний.</span><span class="sxs-lookup"><span data-stu-id="48a2d-209">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

