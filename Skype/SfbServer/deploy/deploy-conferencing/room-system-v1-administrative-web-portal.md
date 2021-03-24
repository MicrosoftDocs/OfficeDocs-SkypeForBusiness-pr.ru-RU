---
title: Развертывание административного веб-портала SRS v1 в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Административный веб-портал Skype для бизнес-серверов Skype Skype Room Systems v1 (SRS v1, ранее известный как Lync Room System) — это веб-портал, который организации могут использовать для обслуживания конференц-залов Skype Room Systems. Администраторы могут использовать административный веб-портал SRS v1 для мониторинга состояния устройств, например с помощью мониторинга аудио- и видео устройств. На этом портале администраторы могут удаленно собирать диагностические сведения для мониторинга состояния конференц-зала.
ms.openlocfilehash: 94e163ccbeff3bde78569aa864b44525b267ccd8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103885"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="9606c-105">Развертывание административного веб-портала SRS v1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9606c-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="9606c-106">Административный веб-портал Skype для бизнес-серверов Skype Skype Room Systems v1 (SRS v1, ранее известный как Lync Room System) — это веб-портал, который организации могут использовать для обслуживания конференц-залов Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="9606c-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="9606c-107">Администраторы могут использовать административный веб-портал SRS v1 для мониторинга состояния устройств, например с помощью мониторинга аудио- и видео устройств.</span><span class="sxs-lookup"><span data-stu-id="9606c-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="9606c-108">На этом портале администраторы могут удаленно собирать диагностические сведения для мониторинга состояния конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="9606c-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="9606c-109">Чтобы использовать эту функцию, необходимо развернуть административный веб-портал SRS v1 на каждом переднем сервере Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9606c-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="9606c-110">Это руководство содержит инструкции для администраторов по установке и настройке административного веб-портала SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="9606c-111">Он предназначен для администраторов, у которых есть знания об администрировании Skype для бизнеса Server, и у которых есть права пользователя администратора, чтобы изменить топологию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9606c-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="9606c-112">После развертывания на сервере административного веб-портала SRS v1 администраторы могут проверить состояние устройств SRS v1, войдя на сайт с собственных компьютеров или ноутбуков.</span><span class="sxs-lookup"><span data-stu-id="9606c-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9606c-113">Скачайте административный веб-портал [Microsoft Skype Room Systems v1 для Skype для бизнеса Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="9606c-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="9606c-114">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="9606c-114">In this topic:</span></span>

- [<span data-ttu-id="9606c-115">Настройка среды для веб-портала администрирования SRS v1</span><span class="sxs-lookup"><span data-stu-id="9606c-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="9606c-116">Установка административного веб-портала SRS v1</span><span class="sxs-lookup"><span data-stu-id="9606c-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="9606c-117">Использование веб-портала администрирования SRS</span><span class="sxs-lookup"><span data-stu-id="9606c-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="9606c-118">Настройка среды для веб-портала администрирования SRS v1</span><span class="sxs-lookup"><span data-stu-id="9606c-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="9606c-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="9606c-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="9606c-120">Чтобы использовать административный веб-портал SRS v1, необходимо установить или настроить следующие необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="9606c-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9606c-121">Если сервер настроен с помощью проверки подлинности Kerberos и NTLM, а SRS запущен на компьютере, не присоединяемом к домену, проверка подлинности Kerberos не пройдет, и пользователь не увидит состояние SRS на административном портале.</span><span class="sxs-lookup"><span data-stu-id="9606c-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="9606c-122">Чтобы устранить эту проблему, настройте сервер с помощью проверки подлинности NTLM или проверки подлинности NTLM и TLS-DSK (без Kerberos) или присоединитесь к компьютеру SRS к домену.</span><span class="sxs-lookup"><span data-stu-id="9606c-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="9606c-123">Установка накопительных обновлений Skype для бизнеса Server в топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9606c-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="9606c-124">Чтобы получить обновление или узнать, что с ним включено, см. в рубли "Обновления для [Skype для бизнеса Server 2015".](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="9606c-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="9606c-125">Создание пользователя Active Directory с поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="9606c-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="9606c-126">Административный веб-портал SRS v1 использует эти учетные данные для запроса сведений из Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9606c-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="9606c-127">Имя пользователя в примерах— LRSApp.</span><span class="sxs-lookup"><span data-stu-id="9606c-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="9606c-128">Создайте группу безопасности Active Directory с именем LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="9606c-129">Создайте группу с групповой областью как global и Group Type as Security.</span><span class="sxs-lookup"><span data-stu-id="9606c-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="9606c-130">Пользователи с поддержкой SIP, добавленные в эту группу, будут уполномочены видеть список комнат и выполнять определенные команды, такие как сбор журналов.</span><span class="sxs-lookup"><span data-stu-id="9606c-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="9606c-131">Создайте группу безопасности Active Directory с именем LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="9606c-132">Создайте группу с групповой областью как global и Group Type как с поддержкой Security.SIP, пользователи, добавленные в эту группу, имеют право использовать все функции портала администрирования в одной комнате Skype.</span><span class="sxs-lookup"><span data-stu-id="9606c-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="9606c-133">Чтобы включить поддержку для массового управления комнатами Skype, обратитесь к шагу 5.</span><span class="sxs-lookup"><span data-stu-id="9606c-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Список групп администраторов с ролью группы безопасности](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="9606c-135">Создайте группу безопасности Active Directory с именем LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="9606c-136">Создайте группу с групповой областью как global и Group Type as Security.</span><span class="sxs-lookup"><span data-stu-id="9606c-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="9606c-137">Пользователи с поддержкой SIP, добавленные в эту группу, могут использовать все функции портала администрирования, включая массовое управление комнатами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9606c-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="9606c-138">Добавьте LRSFullAccessAdminGroup в качестве члена LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Страница LRSSupportAdminGroup Properties Members](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="9606c-140">Создание включенного пользователя Active Directory с именем LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="9606c-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="9606c-141">Добавьте этого пользователя в LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Страница LRSSupportAdminGroup Properties Members](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="9606c-143">Установите [ASP.NET MVC 4 для Visual Studio 2010 sp1 и Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="9606c-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="9606c-144">Установка административного веб-портала SRS v1</span><span class="sxs-lookup"><span data-stu-id="9606c-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="9606c-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="9606c-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="9606c-146">Скачайте административный веб-портал [Microsoft Skype Room Systems v1 для Skype для бизнеса Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="9606c-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="9606c-147">Чтобы установить административный веб-портал SRS v1, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9606c-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="9606c-148">Настройка порта доверенных приложений с помощью следующего команды в оболочке управления серверами Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="9606c-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="9606c-149">Чтобы установить портал залов собраний, загрузите **MeetingRoomPortalInstaller.msi** и запустите его в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="9606c-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="9606c-150">Откройте файл Web.config из следующего расположения:</span><span class="sxs-lookup"><span data-stu-id="9606c-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="9606c-151">%Program Files%\Skype для бизнеса Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="9606c-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="9606c-152">В файле Web.Config измените имя portalUserName на имя пользователя, созданное в шаге 2 в разделе "Настройка среды для административного веб-портала[SRS v1"](room-system-v1-administrative-web-portal.md#Config_Env)(рекомендуемое имя на шаге — LRSApp):</span><span class="sxs-lookup"><span data-stu-id="9606c-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="9606c-153">Так как портал администрирования SRS v1 является доверенным приложением, вам не нужно предоставлять пароль в конфигурации портала.</span><span class="sxs-lookup"><span data-stu-id="9606c-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="9606c-154">Если этот пользователь использует другой регистратор, чем местный регистратор, необходимо указать регистратор для него, добавив следующую строку в файле Web.Config:</span><span class="sxs-lookup"><span data-stu-id="9606c-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="9606c-155">Если используемый порт не превышает 5061, добавьте в файл Web.Config следующую строку:</span><span class="sxs-lookup"><span data-stu-id="9606c-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="9606c-156">Проверка установки административного веб-портала SRS</span><span class="sxs-lookup"><span data-stu-id="9606c-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="9606c-157">Чтобы проверить установку административного веб-портала SRS v1, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9606c-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="9606c-158">На переднем сервере просмотрите следующий URL-адрес:</span><span class="sxs-lookup"><span data-stu-id="9606c-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="9606c-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="9606c-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="9606c-160">Вы не должны видеть ошибок, как показано на следующем изображении:</span><span class="sxs-lookup"><span data-stu-id="9606c-160">You should not see any errors, as shown in the following image:</span></span>

     ![Вход на экран портала администратора системы Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="9606c-162">Если вы не видите ошибок, попробуйте получить доступ к следующему URL-адресу с любого другого компьютера в топологии:</span><span class="sxs-lookup"><span data-stu-id="9606c-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="9606c-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="9606c-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="9606c-164">Чтобы получить доступ к странице, необходимо добавить записи DNS, описанные в["Необходимые DNS-записи](/previous-versions/office/communications-server/bb663700(v=office.12))для автоматического входного клиента".</span><span class="sxs-lookup"><span data-stu-id="9606c-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](/previous-versions/office/communications-server/bb663700(v=office.12))."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="9606c-165">Использование веб-портала администрирования SRS</span><span class="sxs-lookup"><span data-stu-id="9606c-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="9606c-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="9606c-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="9606c-167">После развертывания SRS на сервере можно проверить состояние всех комнат SRS, подписавшись на административный веб-портал SRS v1 из браузера.</span><span class="sxs-lookup"><span data-stu-id="9606c-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="9606c-168">Вход</span><span class="sxs-lookup"><span data-stu-id="9606c-168">Sign in</span></span>

1. <span data-ttu-id="9606c-169">Просмотрите следующий URL-адрес:</span><span class="sxs-lookup"><span data-stu-id="9606c-169">Browse to the following URL:</span></span>

    <span data-ttu-id="9606c-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="9606c-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="9606c-171">Введите учетные данные для учетной записи LRSSupport или учетной записи, добавленной в группу безопасности LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Вход на экран портала администратора системы Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="9606c-173">Сводная страница административного веб-портала SRS</span><span class="sxs-lookup"><span data-stu-id="9606c-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="9606c-174">На странице сводки приводится следующая информация для всех комнат SRS, развернутых на сервере:</span><span class="sxs-lookup"><span data-stu-id="9606c-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="9606c-175">**Тег** Настраиваемая фамилия, которую администратор дает комнате.</span><span class="sxs-lookup"><span data-stu-id="9606c-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="9606c-176">Тег можно установить на портале, нажав на имя комнаты.</span><span class="sxs-lookup"><span data-stu-id="9606c-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="9606c-177">**Здоровье** Состояние здоровья комнаты, которое происходит от состояния Aggregate Health в комнате, которое отображается в разделе Здоровье страницы Параметры комнаты.</span><span class="sxs-lookup"><span data-stu-id="9606c-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="9606c-178">**Следующее собрание** Дата и время следующего собрания.</span><span class="sxs-lookup"><span data-stu-id="9606c-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="9606c-179">**Версия SRS, производитель, модель** Эти значения предустановлены в SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="9606c-180">В зависимости от производителя эти поля могут быть оставлены пустыми.</span><span class="sxs-lookup"><span data-stu-id="9606c-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="9606c-181">**Последнее обновление** Отображает последний раз, когда веб-страница была обновлена.</span><span class="sxs-lookup"><span data-stu-id="9606c-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Сводное представление портала администрирования системы Lync Room](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="9606c-183">Вы увидите меню Bulk Management только в том случае, если вы входите в группу безопасности LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="9606c-184">Сведения о комнатах SRS</span><span class="sxs-lookup"><span data-stu-id="9606c-184">SRS Room Information</span></span>

<span data-ttu-id="9606c-185">Раздел Информация о комнатах портала позволяет просматривать и настраивать отдельные номера SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="9606c-186">Он содержит четыре раздела: "Параметры", "Сведения", "Ведение журнала" и "Здоровье".</span><span class="sxs-lookup"><span data-stu-id="9606c-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="9606c-187">Параметры</span><span class="sxs-lookup"><span data-stu-id="9606c-187">Settings</span></span>

<span data-ttu-id="9606c-188">В разделе Параметры можно установить для комнаты пароль, тег комнаты и уровни громкости по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9606c-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="9606c-189">Если настроить эти параметры, изменения реплицированы только после перезапуска консоли SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="9606c-190">Параметры обновления системы для устройств SRS будут видеться только с помощью выпуска 15.12 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9606c-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Параметры Lync Room System Admin Portal Room](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="9606c-192">Сведения</span><span class="sxs-lookup"><span data-stu-id="9606c-192">Details</span></span>

<span data-ttu-id="9606c-193">В разделе Details приводится сводка параметров комнаты SRS только для чтения, в том числе: время последнего обновления; следующее собрание; последние обновления, обслуживание и калибровка; параметры динамика, микрофона и звонильщика по умолчанию; версия; SIP URI; количество экранов и сведений о каждом экране; состояние и активность.</span><span class="sxs-lookup"><span data-stu-id="9606c-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System Admin Portal Detail View](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="9606c-195">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="9606c-195">Troubleshooting</span></span>

<span data-ttu-id="9606c-196">Раздел Устранение неполадок можно использовать для удаленного сбора журналов и сохранения их в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="9606c-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="9606c-197">Вы также можете перезапустить консоль SRS (пользовательский интерфейс SRS) или перезапустить всю систему.</span><span class="sxs-lookup"><span data-stu-id="9606c-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="9606c-198">Чтобы собрать журналы, устройте путь папки в указанном формате и убедитесь, что в папке есть разрешения на запись, данные учетной записи машины SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="9606c-199">Если размер журнала слишком велик, для завершения сбора журналов может занять до 5 минут.</span><span class="sxs-lookup"><span data-stu-id="9606c-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="9606c-200">Обновление страницы даст вам последний статус.</span><span class="sxs-lookup"><span data-stu-id="9606c-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="9606c-201">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="9606c-201">Health</span></span>

<span data-ttu-id="9606c-202">В разделе Health указывается состояние подключения Skype для бизнеса Server, аудио-устройства, видео устройства, состояния устойчивости и устройства экрана.</span><span class="sxs-lookup"><span data-stu-id="9606c-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="9606c-204">Дополнительные заметки об административном веб-портале</span><span class="sxs-lookup"><span data-stu-id="9606c-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="9606c-205">Изменения параметра применяются только после перезапуска системы SRS.> Если истекает срок действия пароля учетной записи LRSApp, вы не сможете увидеть состояние комнат.</span><span class="sxs-lookup"><span data-stu-id="9606c-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="9606c-206">Настройте пароль учетной записи LRSAppuser таким образом, чтобы он никогда не истекал, или не забудьте обновить пароль, когда он близок к истечении срока действия.> Административный веб-портал SRS поддерживается только для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="9606c-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="9606c-207">Массовое управление</span><span class="sxs-lookup"><span data-stu-id="9606c-207">Bulk management</span></span>

<span data-ttu-id="9606c-208">Массовое управление комнатами SRS — это функция, предназначенная для продвинутых ИТ-администраторов, которая упрощает рабочий процесс и позволяет им с помощью удобного средства экономии времени удаленно управлять несколькими комнатами массово.</span><span class="sxs-lookup"><span data-stu-id="9606c-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="9606c-209">Чтобы увидеть эту функциональность, необходимо, чтобы пользователь был участником специальной группы безопасности **LRSPowerUserAdminsGroup.**</span><span class="sxs-lookup"><span data-stu-id="9606c-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="9606c-210">Количество номеров SRS, которые можно выбрать для массового управления, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="9606c-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="9606c-211">Однако одновременно можно выполнить только одну операцию по массовому управлению.</span><span class="sxs-lookup"><span data-stu-id="9606c-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="9606c-212">Чтобы выполнить операцию по массовому управлению, выберите комнаты, которые необходимо отслеживать, и щелкните меню управления bulk.</span><span class="sxs-lookup"><span data-stu-id="9606c-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="9606c-213">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="9606c-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="9606c-214">Почему я не могу войти на административный веб-портал?</span><span class="sxs-lookup"><span data-stu-id="9606c-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="9606c-215">Когда вы откроете, вы сможете увидеть знак на странице, но при введите учетные данные, вы https://localhost/lrs не можете войти.</span><span class="sxs-lookup"><span data-stu-id="9606c-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="9606c-216">В этом случае необходимо открыть вход на https://FQDNofFEserver/SRS административный веб-портал.</span><span class="sxs-lookup"><span data-stu-id="9606c-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="9606c-217">Почему я не могу видеть SRS v1 на административном веб-портале?</span><span class="sxs-lookup"><span data-stu-id="9606c-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="9606c-218">Убедитесь, что в развертывании есть учетные записи SRS и они создаются в соответствии с рекомендациями развертывания административного веб-портала SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="9606c-219">Убедитесь, что учетные записи SRS будут готовы с помощью Enable-CsMeetingRoom, а не Enable-CsUser на сервере Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9606c-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="9606c-220">Если вы создали учетные записи SRS и не можете видеть учетные записи на административном веб-портале, соберите журналы серверов с помощью средства ведения журнала Skype для бизнеса Server с выбранным компонентом **MeetingPortal** и отправьте их в службу поддержки SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="9606c-221">Если вы создали учетные записи SRS и не можете видеть учетные записи на административном веб-портале, соберите журналы клиентов с помощью Fiddler, а также скопируйте журнал консоли из средств разработки браузера, а затем отправьте их в службу поддержки SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="9606c-222">Вы также можете изменить значение уровня трассировки в Web.config, чтобы получить более подробный журнал.</span><span class="sxs-lookup"><span data-stu-id="9606c-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="9606c-223">Почему я не могу видеть состояние SRS на административном веб-портале?</span><span class="sxs-lookup"><span data-stu-id="9606c-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="9606c-224">Убедитесь, что учетная запись пользователя LRSApp включена с поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="9606c-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="9606c-225">Если у вас еще возникли проблемы, соберите файл **Trace.log** в системе SRS из D:\Tracing\LRSAdminLogs и отправьте его в службу поддержки \, SRS.</span><span class="sxs-lookup"><span data-stu-id="9606c-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="9606c-226">Почему на административном веб-портале не видно меню управления массовыми рассылками для SRS?</span><span class="sxs-lookup"><span data-stu-id="9606c-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="9606c-227">Убедитесь, что учетная запись пользователя LRSApp включена в SIP и входит в группу безопасности LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="9606c-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="9606c-228">Работает ли административный веб-портал SRS v1 с Microsoft Teams Rooms?</span><span class="sxs-lookup"><span data-stu-id="9606c-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="9606c-229">Нет.</span><span class="sxs-lookup"><span data-stu-id="9606c-229">No.</span></span>