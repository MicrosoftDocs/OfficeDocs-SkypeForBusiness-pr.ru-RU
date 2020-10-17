---
title: 'Lync Server 2013: создание или изменение конфигурации партнеров XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1517ef4a7515a46b9237b1788c457c3aee10953d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514806"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="906f5-102">Создание или редактирование конфигурации XMPP-партнеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="906f5-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="906f5-103">_**Последнее изменение темы:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="906f5-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="906f5-104">Microsoft Lync Server 2013 интегрирует в пограничный сервер прокси-сервер Extensible Messaging and Presence Protocol (XMPP) и шлюз XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="906f5-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="906f5-105">Чтобы разрешить подключения от других развертываний XMPP, необходимо настроить XMPP в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="906f5-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="906f5-106">Настраивайте параметры на основе домена XMPP.</span><span class="sxs-lookup"><span data-stu-id="906f5-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="906f5-107">Чтобы создать новую связь с партнером, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="906f5-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="906f5-108">Создание нового федеративного партнера или изменение существующей конфигурации</span><span class="sxs-lookup"><span data-stu-id="906f5-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="906f5-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="906f5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="906f5-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="906f5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="906f5-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="906f5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="906f5-112">На левой панели навигации щелкните **Доступ федерац. и внешний доступ**, затем выберите **Федеративные партнеры XMPP**.</span><span class="sxs-lookup"><span data-stu-id="906f5-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="906f5-113">Чтобы создать новую конфигурацию, нажмите кнопку **Создать**</span><span class="sxs-lookup"><span data-stu-id="906f5-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="906f5-114">Чтобы изменить существующую конфигурацию, выберите конфигурацию и нажмите кнопку **Изменить**</span><span class="sxs-lookup"><span data-stu-id="906f5-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="906f5-115">Чтобы создать или изменить конфигурацию для функции **Федеративные партнеры XMPP**, определите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="906f5-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="906f5-116">**Основной домен** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="906f5-116">**Primary domain** (Required).</span></span> <span data-ttu-id="906f5-117">Основной домен — это базовый домен партнера XMPP.</span><span class="sxs-lookup"><span data-stu-id="906f5-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="906f5-118">Например, в качестве имени домена партнера XMPP можно указать **fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="906f5-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="906f5-119">Это обязательная запись.</span><span class="sxs-lookup"><span data-stu-id="906f5-119">This is a required entry.</span></span>

8.  <span data-ttu-id="906f5-120">**Description**.</span><span class="sxs-lookup"><span data-stu-id="906f5-120">**Description**.</span></span> <span data-ttu-id="906f5-121">В этом поле можно ввести заметки и другие полезные сведения для данной конкретной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="906f5-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="906f5-122">Эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="906f5-122">This entry is optional.</span></span>

9.  <span data-ttu-id="906f5-123">**Дополнительные домены**.</span><span class="sxs-lookup"><span data-stu-id="906f5-123">**Additional domains**.</span></span> <span data-ttu-id="906f5-124">Это домены, которые являются частью домена партнера XMPP, и которые следует включить как часть разрешенного взаимодействия XMPP.</span><span class="sxs-lookup"><span data-stu-id="906f5-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="906f5-125">Например, если вашим основным доменом является **fabrikam.com**, то вы можете перечислить все прочие домены в рамках fabrikam.com, с которыми вы будете связываться через XMPP.</span><span class="sxs-lookup"><span data-stu-id="906f5-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="906f5-126">Например, можно ввести **corp.fabrikam.com** и **it.fabrikam.com** для доменов XMPP "Corporate" и "Information Technologies" в рамках основного домена XMPP fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="906f5-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="906f5-127">**Тип партнера**.</span><span class="sxs-lookup"><span data-stu-id="906f5-127">**Partner type**.</span></span> <span data-ttu-id="906f5-128">**Тип партнера** является обязательным параметром и предоставляет выбор из трех вариантов в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="906f5-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="906f5-129">Необходимо выбрать один из указанных далее типов для описания контактов, которые могут добавляться.</span><span class="sxs-lookup"><span data-stu-id="906f5-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="906f5-130">Можно выбрать один из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="906f5-130">You can select from:</span></span>
    
      - <span data-ttu-id="906f5-131">**Федеративная**.</span><span class="sxs-lookup"><span data-stu-id="906f5-131">**Federated**.</span></span> <span data-ttu-id="906f5-132">Тип **федеративного** партнера — это надежное соединение между развертыванием партнеров Lync Server или Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="906f5-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="906f5-133">**Общедоступный проверенный**.</span><span class="sxs-lookup"><span data-stu-id="906f5-133">**Public verified**.</span></span> <span data-ttu-id="906f5-134">Партнер относится к типу **Общедоступный проверенный**, если контакты, являющиеся частью развертывания, проверяемого поставщиком услуг, можно добавить в список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="906f5-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="906f5-135">Приглашения можно отправлять от пользователя Lync или пользователя Lync, чтобы принимать приглашения от контакта партнера.</span><span class="sxs-lookup"><span data-stu-id="906f5-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="906f5-136">**Общедоступная непроверенная**.</span><span class="sxs-lookup"><span data-stu-id="906f5-136">**Public unverified**.</span></span> <span data-ttu-id="906f5-137">Тип **Общедоступный непроверенный** указывает на отсутствие установленного и проверяемого состояния между двумя развертываниями.</span><span class="sxs-lookup"><span data-stu-id="906f5-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="906f5-138">Пользователь Lync должен пригласить непроверенного контакта для этого контакта, чтобы иметь возможность добавить пользователя Lync в свой список контактов.</span><span class="sxs-lookup"><span data-stu-id="906f5-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="906f5-139">Например, Google Гталк не является общедоступной проверенной службой XMPP, так как она относится к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="906f5-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="906f5-140">Пользователь Гталк не сможет добавить пользователя Lync в качестве контакта, если не было явно отправлено приглашение от пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="906f5-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="906f5-141">Примечания по согласованию потока данных и методам защиты с использованием протоколов TLS и SASL:</span><span class="sxs-lookup"><span data-stu-id="906f5-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="906f5-p110">**XMPP Standards Foundation** (XSF) и **Internet Engineering Task Force** (IETF) определяют набор правил и стандартов для использования клиентских сертификатов TLS, серверных сертификатов TLS и механизма SASL. Использование TLS и SASL является обязательной частью процесса защиты потока данных XMPP. В документе о стандартах XMPP **XEP-0178** “задается рекомендуемый поток данных протокола для использования механизма SASL EXTERNAL с сертификатами PKIX, особенно если XMPP-служба указывает, что TLS является обязательным для согласования”. Согласно документу XSF, PKIX представляет инфраструктуру открытых ключей, называемую также PKI.</span><span class="sxs-lookup"><span data-stu-id="906f5-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="906f5-146">Более подробные сведения о требованиях XMPP см. в XSF-документе XEP-0178.</span><span class="sxs-lookup"><span data-stu-id="906f5-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="906f5-147">Дополнительные сведения см. в статье о лучших методиках использования SASL EXTERNAL с сертификатами согласно XEP-0178.</span><span class="sxs-lookup"><span data-stu-id="906f5-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="906f5-148">Ознакомьтесь с документом IETF "расширенный обмен сообщениями и протоколами присутствия (XMPP): ядро", раздел 5,0, согласование STARTTLS <https://tools.ietf.org/html/rfc6120> .</span><span class="sxs-lookup"><span data-stu-id="906f5-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <https://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="906f5-149">**Согласование TLS**.</span><span class="sxs-lookup"><span data-stu-id="906f5-149">**TLS Negotiation**.</span></span> <span data-ttu-id="906f5-150">Задает правила согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="906f5-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="906f5-151">Служба XMPP может требовать TLS, может установить необязательность TLS, а также вы можете задать, что TLS не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="906f5-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="906f5-152">При выборе значения "Необязательно" решение об обязательности согласования будет принимать служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="906f5-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="906f5-153">Чтобы просмотреть все возможные параметры и сведения о согласовании SASL, TLS и обратный вызов, включая недействительные и известные ошибки, — см. [Параметры согласования для федеративных партнеров XMPP в Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="906f5-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-154">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="906f5-154">**Required**.</span></span> <span data-ttu-id="906f5-155">XMPP-служба нуждается в протоколе согласования TLS.</span><span class="sxs-lookup"><span data-stu-id="906f5-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-156">**Необязательный**параметр.</span><span class="sxs-lookup"><span data-stu-id="906f5-156">**Optional**.</span></span> <span data-ttu-id="906f5-157">XMPP-служба указывает, что протокол согласования TLS является обязательным.</span><span class="sxs-lookup"><span data-stu-id="906f5-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-158">**Не поддерживается**.</span><span class="sxs-lookup"><span data-stu-id="906f5-158">**Not Supported**.</span></span> <span data-ttu-id="906f5-159">XMPP-служба не поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="906f5-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="906f5-160">**Согласование SASL**.</span><span class="sxs-lookup"><span data-stu-id="906f5-160">**SASL negotiation**.</span></span> <span data-ttu-id="906f5-161">Задает правила согласования SASL.</span><span class="sxs-lookup"><span data-stu-id="906f5-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="906f5-162">Служба XMPP может требовать SASL, может установить необязательность SASL, а также вы можете задать, что SASL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="906f5-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="906f5-163">Выбор пункта "Необязательный" означает, что решение об обязательном согласовании принимается на стороне партнерской XMPP-службы.</span><span class="sxs-lookup"><span data-stu-id="906f5-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="906f5-p117">SASL нуждается в TLS. Чтобы использовать SASL, TLS должен быть обязательным или необязательным. Для любой конфигурации, в которой определяется SASL как обязательный или необязательный, требуется поддержка TLS. Если при нажатии кнопки <STRONG>Сохранить</STRONG> для сохранения изменений у вас не задан обязательный или необязательный протокол TLS, вы получите предупреждение о том, что для протокола SASL необходима поддержка TLS, при этом изменения не сохраняются. Чтобы избавиться от этой ошибки, задайте для TLS значение <STRONG>Требуется</STRONG> или <STRONG>Необязательно</STRONG>. Если использование SASL является необязательным и поддержка согласования TLS невозможна, необходимо задать для согласования SASL значение <STRONG>Не поддерживается</STRONG>. Проверьте с помощью XMPP-службы, какие методы согласования необходимы для протоколов TLS и SASL, иначе произойдет нарушение работы службы.</span><span class="sxs-lookup"><span data-stu-id="906f5-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="906f5-171">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="906f5-171">**Required**.</span></span> <span data-ttu-id="906f5-172">XMPP-служба нуждается в протоколе согласования SAS.</span><span class="sxs-lookup"><span data-stu-id="906f5-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-173">**Необязательный**параметр.</span><span class="sxs-lookup"><span data-stu-id="906f5-173">**Optional**.</span></span> <span data-ttu-id="906f5-174">XMPP-служба указывает, что протокол согласования SAS является обязательным.</span><span class="sxs-lookup"><span data-stu-id="906f5-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-175">**Не поддерживается**.</span><span class="sxs-lookup"><span data-stu-id="906f5-175">**Not Supported**.</span></span> <span data-ttu-id="906f5-176">XMPP-служба не поддерживает SAS.</span><span class="sxs-lookup"><span data-stu-id="906f5-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="906f5-177">**Согласование обратный вызов**.</span><span class="sxs-lookup"><span data-stu-id="906f5-177">**Dialback negotiation**.</span></span> <span data-ttu-id="906f5-178">Обратный вызов согласование определяется элементом XSF в документе **КСЕП-220: Server обратный вызов** <http://xmpp.org/extensions/xep-0220.html> .</span><span class="sxs-lookup"><span data-stu-id="906f5-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="906f5-179">Процесс обратного вызова с помощью службы доменных имен (DNS) и полномочного сервера проверяет, от допустимого ли XMPP-партнера пришел запрос.</span><span class="sxs-lookup"><span data-stu-id="906f5-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="906f5-180">Для этого отправляющий сервер создает сообщение особого типа с генерируемым ключом обратного вызова и ищет принимающий сервер в DNS.</span><span class="sxs-lookup"><span data-stu-id="906f5-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="906f5-181">Затем исходный сервер отправляет этот ключ в XML-потоке в результат поиска в DNS, предположительно на принимающий сервер.</span><span class="sxs-lookup"><span data-stu-id="906f5-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="906f5-182">После получения ключа в XML-потоке принимающий сервер не отвечает исходному серверу, а отправляет этот ключ на известный полномочный сервер.</span><span class="sxs-lookup"><span data-stu-id="906f5-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="906f5-183">Полномочный сервер проверяет, является ли ключ допустимым.</span><span class="sxs-lookup"><span data-stu-id="906f5-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="906f5-184">Если ключ недопустимый, то принимающий сервер не отвечает исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="906f5-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="906f5-185">Если ключ допустимый, то принимающий сервер информирует исходный сервер о допустимости удостоверения и ключа и о том, что можно начать беседу.</span><span class="sxs-lookup"><span data-stu-id="906f5-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="906f5-186">**Согласование обратным вызовом** может иметь два следующих допустимых состояния.</span><span class="sxs-lookup"><span data-stu-id="906f5-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-187">**Значение true**.</span><span class="sxs-lookup"><span data-stu-id="906f5-187">**True**.</span></span> <span data-ttu-id="906f5-188">Сервер XMPP настроен на использование согласования с обратным вызовом, когда требуется получить запрос от отправляющего сервера</span><span class="sxs-lookup"><span data-stu-id="906f5-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="906f5-189">**False**.</span><span class="sxs-lookup"><span data-stu-id="906f5-189">**False**.</span></span> <span data-ttu-id="906f5-190">Сервер XMPP не настроен на использование согласования с обратным вызовом, поэтому когда требуется получить запрос от отправляющего сервера, этот запрос игнорируется</span><span class="sxs-lookup"><span data-stu-id="906f5-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

