---
title: 'Lync Server 2013: Создание параметров конфигурации регистратора'
description: 'Lync Server 2013: Создание параметров конфигурации регистратора.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ada10302b3c2319e0f713ce2d3bea00b6fed126
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548705"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9db3f-103">Создание параметров конфигурации регистратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9db3f-103">Create Registrar configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9db3f-104">_**Последнее изменение темы:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="9db3f-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="9db3f-p101">Регистратор можно использовать для настройки способов проверки подлинности прокси-сервера. Заданный протокол проверки подлинности определяет, какой тип запросов серверы в пуле выдают клиентам. Далее приводятся доступные протоколы.</span><span class="sxs-lookup"><span data-stu-id="9db3f-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="9db3f-108">Проверка **подлинности Kerberos**     Это наиболее надежная схема проверки подлинности на основе паролей, доступная клиентам, но обычно она доступна только для корпоративных клиентов, так как для этого требуется подключение клиента к центру распространения ключей (контроллер домена Kerberos).</span><span class="sxs-lookup"><span data-stu-id="9db3f-108">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="9db3f-109">Этот протокол подходит, если сервер проверяет подлинность только клиентов предприятия.</span><span class="sxs-lookup"><span data-stu-id="9db3f-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="9db3f-110">**NTLM**     Это проверка подлинности на основе паролей, доступная для клиентов, использующих для пароля схему хеширования "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="9db3f-110">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="9db3f-111">Это единственная форма проверки подлинности, доступная клиентам без подключения к центру распространения ключей (контроллеру домена Kerberos), таким как удаленные пользователи.</span><span class="sxs-lookup"><span data-stu-id="9db3f-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="9db3f-112">Если сервер проверяет подлинность только удаленных пользователей, то следует выбрать NTLM.</span><span class="sxs-lookup"><span data-stu-id="9db3f-112">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="9db3f-113">**Проверка подлинности сертификата**     Это новый способ проверки подлинности, когда серверу требуется получить сертификаты от клиентов Lync Phone Edition, общедоступные телефоны, Lync 2013 и приложение Lync Windows для магазина.</span><span class="sxs-lookup"><span data-stu-id="9db3f-113">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="9db3f-114">На клиентах Lync Phone Edition после входа пользователя в систему и успешной проверки подлинности с помощью предоставления персонального идентификационного номера (ПИН-кода), Lync Server 2013 затем подготавливает универсальный код ресурса (URI) SIP к телефону и предоставляет сертификат пользователя, подписанный сервером Lync (например, SN=joe@contoso.com), на телефоне.</span><span class="sxs-lookup"><span data-stu-id="9db3f-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="9db3f-115">Этот сертификат используется для проверки подлинности с помощью регистратора и веб-служб</span><span class="sxs-lookup"><span data-stu-id="9db3f-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9db3f-p105">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9db3f-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="9db3f-120">Если вы будете использовать приложения Lync для Магазина Windows, необходимо включить проверку подлинности с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="9db3f-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="9db3f-121">Для создания нового регистратора выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9db3f-121">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="9db3f-122">Создание новых параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="9db3f-122">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="9db3f-123">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9db3f-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9db3f-124">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9db3f-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9db3f-125">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9db3f-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9db3f-126">В левой панели навигации последовательно выберите пункты **Безопасность** и **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="9db3f-126">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="9db3f-127">На странице **регистратора** нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9db3f-127">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="9db3f-128">В поле **выбора службы** выберите службу, к которой должен быть применен регистратор, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9db3f-128">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="9db3f-129">В разделе **Настройка нового регистратора** установите какие-либо из следующих флажков, в зависимости от возможностей клиентов и поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="9db3f-129">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="9db3f-130">**Включить проверку подлинности Kerberos** — чтобы серверы в пуле выдавали запросы с использованием проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9db3f-130">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="9db3f-131">**Включить проверку подлинности NTLM** — чтобы серверы в пуле выдавали запросы с использованием NTLM.</span><span class="sxs-lookup"><span data-stu-id="9db3f-131">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="9db3f-132">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="9db3f-132">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="9db3f-133">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="9db3f-133">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

