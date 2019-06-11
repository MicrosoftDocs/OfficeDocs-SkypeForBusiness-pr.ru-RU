---
title: 'Lync Server 2013: Создание параметров конфигурации регистратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4db30-102">Создание параметров конфигурации регистратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4db30-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4db30-103">_**Тема последнего изменения:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="4db30-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="4db30-p101">Регистратор можно использовать для настройки способов проверки подлинности прокси-сервера. Заданный протокол проверки подлинности определяет, какой тип запросов серверы в пуле выдают клиентам. Далее приводятся доступные протоколы.</span><span class="sxs-lookup"><span data-stu-id="4db30-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="4db30-107">**Kerberos**   — это надежная схема проверки подлинности на основе паролей, доступная для клиентов, но она обычно доступна только для корпоративных клиентов, так как для этого требуется подключение клиента к центру распространения ключей (контроллеру домена Kerberos).</span><span class="sxs-lookup"><span data-stu-id="4db30-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="4db30-108">Это значение можно выбрать в том случае, если на сервере проверяется подлинность только корпоративных клиентов.</span><span class="sxs-lookup"><span data-stu-id="4db30-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="4db30-109">**NTLM**   это проверка подлинности на основе пароля, доступная для клиентов, использующих в пароле схему хеширования с запросом ответа.</span><span class="sxs-lookup"><span data-stu-id="4db30-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="4db30-110">Это единственная форма проверки подлинности, доступная клиентам без подключения к центру распространения ключей (контроллеру домена Kerberos), в том числе удаленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="4db30-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="4db30-111">Если на сервере проверяется подлинность только удаленных пользователей, следует выбрать значение NTLM.</span><span class="sxs-lookup"><span data-stu-id="4db30-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="4db30-112">**Проверка**   подлинности сертификата. это новый способ проверки подлинности, когда сервер должен получить сертификаты от клиентов Lync Phone Edition, обычных телефонов, Lync 2013 и приложения Lync из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="4db30-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="4db30-113">На клиентах Lync Phone Edition после входа пользователя в систему и успешной проверки подлинности, предоставляя персональный идентификационный номер (ПИН-код), Lync Server 2013 затем подготавливает универсальный код ресурса (URI) SIP к телефону и подготавливает сертификат, подписанный сервером Lync, или сертификат пользователя. с помощью которого вы указываете Джо (например: SN=joe@contoso.com) на телефон.</span><span class="sxs-lookup"><span data-stu-id="4db30-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="4db30-114">Этот сертификат применяется при проверке подлинности с помощью регистратора и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="4db30-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4db30-p105">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4db30-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="4db30-119">Если вы используете приложения Lync из Магазина Windows, необходимо включить проверку подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="4db30-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="4db30-120">Для создания нового регистратора выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4db30-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="4db30-121">Создание параметров конфигурации нового регистратора</span><span class="sxs-lookup"><span data-stu-id="4db30-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="4db30-122">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4db30-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4db30-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4db30-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4db30-124">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4db30-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4db30-125">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="4db30-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="4db30-126">На странице **Регистратор** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4db30-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="4db30-127">В поле **Выбор службы** выберите службу, к которой требуется применить регистратор, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4db30-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="4db30-128">На странице **Создание новой настройки регистратора** установите один или несколько флажков в зависимости от возможностей клиентов.</span><span class="sxs-lookup"><span data-stu-id="4db30-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="4db30-129">**Включить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4db30-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="4db30-130">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="4db30-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="4db30-131">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="4db30-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="4db30-132">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4db30-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

