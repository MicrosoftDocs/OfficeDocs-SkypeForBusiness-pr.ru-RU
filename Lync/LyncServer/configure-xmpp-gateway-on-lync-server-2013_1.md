---
title: Настройка шлюза XMPP в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5735c9e4786548ce7b12ab82327ffc72c27873bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="bf1b7-102">Настройка шлюза XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1b7-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf1b7-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bf1b7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bf1b7-104">При настройке политик для поддержки федеративных контактов по протоколу XMPP) политики применяются к пользователям федеративных доменов, но не к пользователям поставщиков услуг обмена мгновенными сообщениями по протоколу SIP (например, Windows Live) или федеративных доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="bf1b7-105">Вы настраиваете федеративного партнера XMPP для каждого федеративного домена XMPP, для которого необходимо разрешить взаимодействие и добавление контактов пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="bf1b7-106">После того как политики будут настроены, дополнительные задачи включают настройку сертификатов шлюза XMPP, развертывание шлюза Lync Server 2013 XMPP и, наконец, обновление записей DNS для шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="bf1b7-107">Настройка сертификатов шлюза XMPP на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1b7-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="bf1b7-108">На пограничном сервере в мастере развертывания рядом с пунктом **Шаг 3. Запрос, установка или назначение сертификатов** нажмите кнопку **Повторный запуск**.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="bf1b7-109">Если развертывание пограничного сервера выполняется впервые, то вместо кнопки "Повторный запуск" будет отображаться кнопка "Запуск".</span><span class="sxs-lookup"><span data-stu-id="bf1b7-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="bf1b7-110">На странице **Available Certificate Tasks** (Доступные задачи сертификатов) щелкните команду **Create a new certificate request** (Создать новый запрос сертификата).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="bf1b7-111">На странице **запроса сертификата** выберите пункт **External Edge Certificate** (Внешний сертификат пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="bf1b7-112">На странице **Отложенный или немедленный запрос** установите флажок **Подготовить запрос сейчас, чтобы отправить его позже**.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="bf1b7-113">На странице **файл запроса сертификата** введите полный путь и имя файла, в который будет сохранен запрос (например, c:\\CERT\_ексернал\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="bf1b7-114">На странице **указания альтернативного шаблона сертификата** для использования шаблона, отличного от шаблона WebServer по умолчанию, установите флажок **Use alternative certificate template for the selected certification authority** (Использовать альтернативный шаблон сертификата для выбранного центра сертификации).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="bf1b7-115">На странице **настроек имени и безопасности** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="bf1b7-116">В поле **Понятное имя** введите отображаемое имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="bf1b7-117">В поле **Длина в битах** укажите длину в битах (обычно используется значение по умолчанию 2048).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="bf1b7-118">Убедитесь, что флажок **Mark certificate private key as exportable** (Пометить закрытый ключ сертификата как экспортируемый) установлен.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="bf1b7-119">На странице **сведений об организации** укажите имя организации и подразделения (например, отделения или отдела).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="bf1b7-120">На странице **сведений о местоположении** укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="bf1b7-p102">На странице **имени субъекта и альтернативных имен субъекта** отображаются сведения, автоматически заполненные мастером. Если требуются дополнительные альтернативные имена субъекта, то они указываются в следующих двух действиях.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="bf1b7-123">На странице **Параметры домена SIP в альтернативных именах субъектов (SAN)** установите флажок домен, чтобы добавить SIP. \<sipdomain\> запись в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="bf1b7-124">На странице **Настройка дополнительных альтернативных имен субъекта** укажите все необходимые дополнительные альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="bf1b7-p103">Если устанавливается прокси-сервер XMPP, то по умолчанию в записях SAN заполняется имя домена (например, contoso.com). Если требуются дополнительные записи, добавьте их сейчас.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-p103">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="bf1b7-127">На странице **Сводка о запросе** просмотрите сведения о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="bf1b7-128">После завершения выполнения команд можно **Просмотреть журнал** или нажать кнопку **Далее** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="bf1b7-129">На странице **Файл запроса сертификата** можно просмотреть файл сформированного запроса на подписание сертификата (CSR), нажав кнопку просмотра или выйдя из мастера сертификатов нажатием кнопки **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="bf1b7-130">Скопируйте файл запроса и отправьте его на свой общедоступный сервер сертификации.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="bf1b7-p104">После получения, импорта и назначения общедоступного сертификата необходимо остановить и перезапустить службы пограничного сервера. Это можно сделать, введя в консоли управления Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf1b7-p104">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="bf1b7-133">Настройка нового шлюза XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1b7-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="bf1b7-134">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="bf1b7-135">В левой панели навигации нажмите **Federation and External Access** (Федерация и внешний доступ), а затем выберите пункт **XMPP Federated Partners** (Федеративные партнеры XMPP).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="bf1b7-136">Чтобы создать новую конфигурацию, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="bf1b7-137">Задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-137">Define the following settings:</span></span>

5.  <span data-ttu-id="bf1b7-138">**Основной домен**     (обязательно).</span><span class="sxs-lookup"><span data-stu-id="bf1b7-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="bf1b7-139">Основной домен — это базовый домен партнера XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="bf1b7-140">Например, в качестве имени домена партнера XMPP можно указать **fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="bf1b7-141">Это обязательная запись.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-141">This is a required entry.</span></span>

6.  <span data-ttu-id="bf1b7-142">**Описание**   описание для заметок или других идентифицирующих сведений для этой конкретной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="bf1b7-143">Эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-143">This entry is optional.</span></span>

7.  <span data-ttu-id="bf1b7-144">**Дополнительные**   домены дополнительные домены — это домены, которые входят в состав домена партнера XMPP, который должен быть включен в состав разрешенного обмена сообщениями XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="bf1b7-145">Например, если в качестве основного домена указан **fabrikam.com**, то может потребоваться перечислить все остальные домены, входящие в домен fabrikam.com, с которыми будет осуществляться взаимодействие посредством XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="bf1b7-146">**Тип**   партнера **тип партнера** является обязательным параметром.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="bf1b7-147">Необходимо выбрать один из указанных далее типов для описания контактов, которые могут добавляться.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="bf1b7-148">Можно выбрать один из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-148">You can select from:</span></span>
    
      - <span data-ttu-id="bf1b7-149">**Федеративная** Тип **федеративного** партнера представляет высокий уровень доверия между развертыванием Lync Server и партнером XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="bf1b7-150">Этот тип партнера рекомендуется для федерации с серверами XMPP в одном предприятии или при наличии установленного бизнес-сотрудничества.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="bf1b7-151">Контакты XMPP, указанные в федеративных партнерах, могут выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="bf1b7-152">Добавлять контакты Lync и просматривать их сведения о присутствии без необходимости экспресс-авторизации пользователем Lync.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="bf1b7-153">Отправлять мгновенные сообщения контактам Lync независимо от того, были ли они добавлены пользователями Lync в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="bf1b7-154">Просматривать заметки о состоянии пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="bf1b7-155">**Общедоступный** **проверенный партнер —** это общедоступный поставщик XMPP, который является доверенным для проверки подлинности пользователей. </span><span class="sxs-lookup"><span data-stu-id="bf1b7-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="bf1b7-156">Контакты XMPP в общедоступных проверенных сетях могут добавлять контакты Lync и просматривать их сведения о присутствии, а также отправлять им мгновенные сообщения без экспресс-авторизации пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="bf1b7-157">Контакты XMPP в общедоступных проверенных сетях никогда не видят заметки о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="bf1b7-158">Это значение не является рекомендуемым.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="bf1b7-p111">**Общедоступный непроверенный**. **Общедоступный непроверенный** партнер — это общедоступный поставщик XMPP, ненадежный с точки зрения проверки удостоверений его пользователей.  XMPP-пользователи в общедоступных непроверенных сетях не могут взаимодействовать с пользователями Lync, пока пользователи Lync явным образом не разрешат это взаимодействие, добавляя XMPP-пользователей в свои списки контактов. XMPP-пользователи в общедоступных непроверенных сетях не могут видеть примечания о состоянии пользователей Lync. Это значение рекомендуется для любой федерации с общедоступными поставщиками XMPP, такими как Google Talk.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-p111">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="bf1b7-163">**Тип подключения:** определяет различные правила и параметры обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="bf1b7-164">**Согласование TLS определяет**   правила согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="bf1b7-165">Служба XMPP может требовать TLS, может установить необязательность TLS, а также вы можете задать, что TLS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="bf1b7-166">При выборе значения "Необязательно" решение об обязательности согласования будет принимать служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="bf1b7-167">Чтобы просмотреть все возможные параметры и сведения о согласовании SASL, TLS и обратный вызов, включая недействительные и известные ошибки, — см. [Параметры согласования для федеративных партнеров XMPP в Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="bf1b7-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="bf1b7-168">**Требуется**   служба XMPP требует согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="bf1b7-169">**Необязательная**   служба XMPP указывает, что протокол TLS является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="bf1b7-170">**Не поддерживается**   служба XMPP не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="bf1b7-171">**Согласование SASL определяет**   правила согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="bf1b7-172">Служба XMPP может требовать SASL, может установить необязательность SASL, а также вы можете задать, что SASL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="bf1b7-173">При выборе значения "Необязательно" решение об обязательности согласования будет принимать служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="bf1b7-174">**Required**   служба XMPP требует согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="bf1b7-175">**Необязательная**   служба XMPP указывает, что SASL является обязательным по отношению к согласованию.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="bf1b7-176">**Не поддерживается**   служба XMPP не поддерживает SASL.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="bf1b7-177">**Согласование сервера поддержки обратный вызов** Процесс согласования сервера поддержки обратный вызов использует систему доменных имен (DNS) и удостоверяющий сервер для проверки того, что запрос пришел от действительного партнера XMPP.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="bf1b7-178">Для этого исходный сервер создает сообщение определенного типа с созданным ключом обратного вызова и ищет принимающий сервер в DNS.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="bf1b7-179">Затем исходный сервер отправляет этот ключ в XML-потоке в результат поиска в DNS, предположительно на принимающий сервер.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="bf1b7-180">После получения ключа в XML-потоке принимающий сервер не отвечает исходному серверу, а отправляет этот ключ на известный полномочный сервер.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="bf1b7-181">Полномочный сервер проверяет, является ли ключ допустимым.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="bf1b7-182">Если ключ недопустимый, то принимающий сервер не отвечает исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="bf1b7-183">Если ключ допустимый, то принимающий сервер информирует исходный сервер о допустимости удостоверения и ключа и о том, что можно начать беседу.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="bf1b7-184">**Согласование обратным вызовом** может иметь два следующих допустимых состояния.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="bf1b7-185">**True**   . сервер XMPP настроен на использование согласования обратный вызов, если запрос должен быть получен с исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="bf1b7-186">**False**   . сервер XMPP не настроен на использование согласования обратный вызов, и если запрос должен быть получен с исходного сервера, он будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="bf1b7-187">Нажмите кнопку **Commit** (Сохранить), чтобы сохранить изменения в политике на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="bf1b7-188">Обновление записей DNS для шлюза XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1b7-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="bf1b7-189">Чтобы настроить DNS для Федерации XMPP, добавьте следующую запись SRV к внешней DNS:\_XMPP-Server. \_TCP. \<доменное\> имя. запись SRV будет РАЗРЕШАТЬся в полное доменное имя пограничного сервера доступа с портом 5269.</span><span class="sxs-lookup"><span data-stu-id="bf1b7-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

