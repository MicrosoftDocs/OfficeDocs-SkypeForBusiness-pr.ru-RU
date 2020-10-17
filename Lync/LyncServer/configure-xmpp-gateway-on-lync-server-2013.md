---
title: Настройка шлюза XMPP в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dc21ddbbfd5d65d6834ffa5a6181c5e4a13b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503186"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="34f27-102">Настройка шлюза XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f27-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34f27-103">_**Последнее изменение темы:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="34f27-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="34f27-104">Последние действия для переноса шлюза XMPP: Настройка сертификатов для пограничного сервера Lync Server 2013, развертывание шлюза Lync Server 2013 XMPP и обновление записей DNS для шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="34f27-105">Эти действия должны выполняться параллельно, чтобы минимизировать время простоя шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="34f27-106">Перед выполнением этих действий все пользователи должны быть перемещены в развертывание Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34f27-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="34f27-107">Федерация XMPP не поддерживается для пользователей, которые размещены на устройствах для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="34f27-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="34f27-108">Это относится как к просмотру сведений о присутствии, так и при обмене МГНОВЕНными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="34f27-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="34f27-109">Настройка сертификатов шлюза XMPP на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f27-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="34f27-110">На пограничном сервере в мастере развертывания рядом с пунктом **Шаг 3. Запрос, установка или назначение сертификатов** нажмите кнопку **Повторный запуск**.</span><span class="sxs-lookup"><span data-stu-id="34f27-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="34f27-111">Если развертывание пограничного сервера выполняется впервые, то вместо кнопки "Повторный запуск" будет отображаться кнопка "Запуск".</span><span class="sxs-lookup"><span data-stu-id="34f27-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="34f27-112">На странице **Available Certificate Tasks** (Доступные задачи сертификатов) щелкните команду **Create a new certificate request** (Создать новый запрос сертификата).</span><span class="sxs-lookup"><span data-stu-id="34f27-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="34f27-113">На странице **запроса сертификата** выберите пункт **External Edge Certificate** (Внешний сертификат пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="34f27-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="34f27-114">На странице **Отложенный или немедленный запрос** установите флажок **Подготовить запрос сейчас, чтобы отправить его позже**.</span><span class="sxs-lookup"><span data-stu-id="34f27-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="34f27-115">На странице **файл запроса сертификата** введите полный путь и имя файла, в который будет сохранен запрос (например, c: \\ CERT \_ ексернал \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="34f27-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="34f27-116">На странице **указания альтернативного шаблона сертификата** для использования шаблона, отличного от шаблона WebServer по умолчанию, установите флажок **Use alternative certificate template for the selected certification authority** (Использовать альтернативный шаблон сертификата для выбранного центра сертификации).</span><span class="sxs-lookup"><span data-stu-id="34f27-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="34f27-117">На странице **настроек имени и безопасности** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34f27-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="34f27-118">В поле **Понятное имя** введите отображаемое имя для сертификата.</span><span class="sxs-lookup"><span data-stu-id="34f27-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="34f27-119">В поле **Длина в битах** укажите длину в битах (обычно используется значение по умолчанию 2048).</span><span class="sxs-lookup"><span data-stu-id="34f27-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="34f27-120">Убедитесь, что флажок **Mark certificate private key as exportable** (Пометить закрытый ключ сертификата как экспортируемый) установлен.</span><span class="sxs-lookup"><span data-stu-id="34f27-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="34f27-121">На странице **сведений об организации** укажите имя организации и подразделения (например, отделения или отдела).</span><span class="sxs-lookup"><span data-stu-id="34f27-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="34f27-122">На странице **сведений о местоположении** укажите сведения о местоположении.</span><span class="sxs-lookup"><span data-stu-id="34f27-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="34f27-p103">На странице **имени субъекта и альтернативных имен субъекта** отображаются сведения, автоматически заполненные мастером. Если требуются дополнительные альтернативные имена субъекта, то они указываются в следующих двух действиях.</span><span class="sxs-lookup"><span data-stu-id="34f27-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="34f27-125">На странице **Параметры домена SIP в альтернативных именах субъектов (SAN)** установите флажок домен, чтобы добавить SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="34f27-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="34f27-126">запись в список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="34f27-126">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="34f27-127">На странице **Настройка дополнительных альтернативных имен субъекта** укажите все необходимые дополнительные альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="34f27-127">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="34f27-p105">Если устанавливается прокси-сервер XMPP, то по умолчанию в записях SAN заполняется имя домена (например, contoso.com). Если требуются дополнительные записи, добавьте их сейчас.</span><span class="sxs-lookup"><span data-stu-id="34f27-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="34f27-130">На странице **сводки по запросу** просмотрите сведения о сертификате, которые будут использоваться для создания запроса.</span><span class="sxs-lookup"><span data-stu-id="34f27-130">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="34f27-131">После завершения выполнения команд можно **просмотреть журнал** или нажат кнопку "Далее" для продолжения.</span><span class="sxs-lookup"><span data-stu-id="34f27-131">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="34f27-132">На странице **файла запроса сертификата** можно просмотреть созданный файл запроса подписи сертификата (CSR-файл), нажав кнопку **Просмотр**, или выйти из мастера сертификатов, нажав кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="34f27-132">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="34f27-133">Скопируйте файл запроса и отправьте его в ваш общедоступный центр сертификации.</span><span class="sxs-lookup"><span data-stu-id="34f27-133">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="34f27-p106">После получения, импорта и назначения общедоступного сертификата необходимо остановить и перезапустить службы пограничного сервера. Это можно сделать, введя в консоли управления Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34f27-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="34f27-136">Настройка нового шлюза XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f27-136">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="34f27-137">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34f27-137">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="34f27-138">В левой панели навигации нажмите **Federation and External Access** (Федерация и внешний доступ), а затем выберите пункт **XMPP Federated Partners** (Федеративные партнеры XMPP).</span><span class="sxs-lookup"><span data-stu-id="34f27-138">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="34f27-139">Чтобы создать новую конфигурацию, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="34f27-139">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="34f27-140">Задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="34f27-140">Define the following settings:</span></span>

5.  <span data-ttu-id="34f27-141">**Основной домен**     (Обязательно).</span><span class="sxs-lookup"><span data-stu-id="34f27-141">**Primary domain**    (Required).</span></span> <span data-ttu-id="34f27-142">Основной домен — это базовый домен партнера XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-142">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="34f27-143">Например, в качестве имени домена партнера XMPP можно указать **fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="34f27-143">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="34f27-144">Это обязательная запись.</span><span class="sxs-lookup"><span data-stu-id="34f27-144">This is a required entry.</span></span>

6.  <span data-ttu-id="34f27-145">**Description (описание**     ) Описание предназначено для заметок или других идентифицирующих сведений для этой конкретной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34f27-145">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="34f27-146">Эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="34f27-146">This entry is optional.</span></span>

7.  <span data-ttu-id="34f27-147">**Дополнительные домены**     Дополнительные домены — это домены, которые входят в состав домена партнера XMPP, который должен быть включен в состав разрешенного обмена сообщениями XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-147">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="34f27-148">Например, если в качестве основного домена указан **fabrikam.com**, то может потребоваться перечислить все остальные домены, входящие в домен fabrikam.com, с которыми будет осуществляться взаимодействие посредством XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-148">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="34f27-149">**Тип партнера**     **Тип партнера** — обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="34f27-149">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="34f27-150">Необходимо выбрать один из указанных далее типов для описания контактов, которые могут добавляться.</span><span class="sxs-lookup"><span data-stu-id="34f27-150">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="34f27-151">Можно выбрать один из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="34f27-151">You can select from:</span></span>
    
      - <span data-ttu-id="34f27-152">**Федеративная**     Тип **федеративного** партнера представляет высокий уровень доверия между развертыванием Lync Server и партнером XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-152">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="34f27-153">Этот тип партнера рекомендуется для федерации с серверами XMPP в одном предприятии или при наличии установленного бизнес-сотрудничества.</span><span class="sxs-lookup"><span data-stu-id="34f27-153">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="34f27-154">Контакты XMPP, указанные в федеративных партнерах, могут выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34f27-154">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="34f27-155">Добавлять контакты Lync и просматривать их сведения о присутствии без необходимости экспресс-авторизации пользователем Lync.</span><span class="sxs-lookup"><span data-stu-id="34f27-155">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="34f27-156">Отправлять мгновенные сообщения контактам Lync независимо от того, были ли они добавлены пользователями Lync в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="34f27-156">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="34f27-157">Просматривать заметки о состоянии пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="34f27-157">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="34f27-158">**Общедоступная проверка**     **Общедоступный проверенный** партнер — это общедоступный поставщик XMPP, который является доверенным для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="34f27-158">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="34f27-159">Контакты XMPP в общедоступных проверенных сетях могут добавлять контакты Lync и просматривать их сведения о присутствии, а также отправлять им мгновенные сообщения без экспресс-авторизации пользователями Lync.</span><span class="sxs-lookup"><span data-stu-id="34f27-159">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="34f27-160">Контакты XMPP в общедоступных проверенных сетях никогда не видят заметки о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="34f27-160">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="34f27-161">Эта установка не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="34f27-161">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="34f27-162">**Общедоступная непроверенная**     **Общедоступный непроверенный** партнер — это общедоступный поставщик XMPP, который не является доверенным для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="34f27-162">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="34f27-163">Пользователи XMPP в общедоступных непроверенных сетях не могут взаимодействовать с пользователями Lync, пока пользователь Lync не выполнит их экспресс-авторизацию путем добавления их в список контактов.</span><span class="sxs-lookup"><span data-stu-id="34f27-163">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="34f27-164">Пользователи XMPP в общедоступных непроверенных сетях никогда не видят заметки о состоянии пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="34f27-164">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="34f27-165">Эта установка рекомендуется для федерации с общедоступными поставщиками XMPP, такими как Google Talk.</span><span class="sxs-lookup"><span data-stu-id="34f27-165">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="34f27-166">**Тип подключения:** задает разные правила и параметры обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="34f27-166">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="34f27-167">**Согласование TLS**     Определяет правила согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="34f27-167">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="34f27-168">Служба XMPP может требовать TLS, может установить необязательность TLS, а также вы можете задать, что TLS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="34f27-168">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="34f27-169">При выборе значения "Необязательно" решение об обязательности согласования будет принимать служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-169">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="34f27-170">Чтобы просмотреть все возможные параметры и сведения о согласовании SASL, TLS и обратный вызов, включая недействительные и известные ошибки, — см. [Параметры согласования для федеративных партнеров XMPP в Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="34f27-170">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-171">**Required (обязательный**     ) Для службы XMPP требуется согласование TLS.</span><span class="sxs-lookup"><span data-stu-id="34f27-171">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-172">**Необязательное требование**     Служба XMPP указывает, что протокол TLS является обязательным для согласования.</span><span class="sxs-lookup"><span data-stu-id="34f27-172">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-173">**Не поддерживается**     Служба XMPP не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="34f27-173">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="34f27-174">**Согласование SASL**     Определяет правила согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="34f27-174">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="34f27-175">Служба XMPP может требовать SASL, может установить необязательность SASL, а также вы можете задать, что SASL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="34f27-175">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="34f27-176">При выборе значения "Необязательно" решение об обязательности согласования будет принимать служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-176">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-177">**Required (обязательный**     ) Службе XMPP требуется согласование SASL.</span><span class="sxs-lookup"><span data-stu-id="34f27-177">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-178">**Необязательное требование**     Служба XMPP указывает, что SASL является обязательным по отношению к согласованию.</span><span class="sxs-lookup"><span data-stu-id="34f27-178">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-179">**Не поддерживается**     Служба XMPP не поддерживает SASL.</span><span class="sxs-lookup"><span data-stu-id="34f27-179">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="34f27-180">**Согласование сервера поддержки обратный вызов** Процесс согласования сервера поддержки обратный вызов использует систему доменных имен (DNS) и удостоверяющий сервер для проверки того, что запрос пришел от действительного партнера XMPP.</span><span class="sxs-lookup"><span data-stu-id="34f27-180">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="34f27-181">Для этого исходный сервер создает сообщение определенного типа с созданным ключом обратного вызова и ищет принимающий сервер в DNS.</span><span class="sxs-lookup"><span data-stu-id="34f27-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="34f27-182">Затем исходный сервер отправляет этот ключ в XML-потоке в результат поиска в DNS, предположительно на принимающий сервер.</span><span class="sxs-lookup"><span data-stu-id="34f27-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="34f27-183">После получения ключа в XML-потоке принимающий сервер не отвечает исходному серверу, а отправляет этот ключ на известный полномочный сервер.</span><span class="sxs-lookup"><span data-stu-id="34f27-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="34f27-184">Полномочный сервер проверяет, является ли ключ допустимым.</span><span class="sxs-lookup"><span data-stu-id="34f27-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="34f27-185">Если ключ недопустимый, то принимающий сервер не отвечает исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="34f27-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="34f27-186">Если ключ допустимый, то принимающий сервер информирует исходный сервер о допустимости удостоверения и ключа и о том, что можно начать беседу.</span><span class="sxs-lookup"><span data-stu-id="34f27-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="34f27-187">**Согласование обратным вызовом** может иметь два следующих допустимых состояния.</span><span class="sxs-lookup"><span data-stu-id="34f27-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-188">**Значение true**     Сервер XMPP настроен на использование согласования обратный вызов, если запрос должен быть получен с исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="34f27-188">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="34f27-189">**False (ложь**     ) Сервер XMPP не настроен на использование согласования обратный вызов, и если запрос должен быть получен с исходного сервера, он будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="34f27-189">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="34f27-190">Нажмите кнопку **Commit** (Сохранить), чтобы сохранить изменения в политике на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="34f27-190">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="34f27-191">Обновление записей DNS для шлюза XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34f27-191">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="34f27-192">Чтобы настроить DNS для Федерации XMPP, добавьте следующую запись SRV к внешней DNS: \_ XMPP-Server. \_ семейства.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="34f27-192">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="34f27-193">Запись SRV будет разрешаться в полное доменное имя пограничного сервера доступа, при этом значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="34f27-193">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

