---
title: Использование Microsoft 365 и настраиваемой соединители
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Соединители помогают поддерживать текущую работу команды, предоставляя контент и обновления из служб, которые вы часто используете, непосредственно в канале.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3e6e65c3462242b82691a292770de684b6c4404b
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684246"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="b9e19-103">Используйте Microsoft 365 и пользовательские соединители в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9e19-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="b9e19-104">Соединитетели обеспечивают постоянное обновление команды, доставляя часто используемое содержимое и обновления служб непосредственно в канал.</span><span class="sxs-lookup"><span data-stu-id="b9e19-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="b9e19-105">Благодаря соединительным Microsoft Teams пользователи могут получать обновления от популярных служб, таких как Trello, Wunderlist, GitHub и Azure DevOps Services в потоке чата в своей команде.</span><span class="sxs-lookup"><span data-stu-id="b9e19-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="b9e19-106">Любой участник группы может подключить свою команду к популярным облачным службам с помощью соединитеров, если это разрешает группа, и все участники группы будут уведомлены о действиях в этой службе.</span><span class="sxs-lookup"><span data-stu-id="b9e19-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="b9e19-107">Соединитетели продолжат работать даже после того, как участник, изначально настроивший соединителю, покинул ее.</span><span class="sxs-lookup"><span data-stu-id="b9e19-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="b9e19-108">Любой участник группы с разрешениями на добавление и удаление может изменять настройки соединители другими участниками.</span><span class="sxs-lookup"><span data-stu-id="b9e19-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="b9e19-109">Microsoft 365 можно использовать как с группами Microsoft Teams, так и Microsoft 365, чтобы всем участникам было проще синхронизироваться и быстро получать актуальные сведения.</span><span class="sxs-lookup"><span data-stu-id="b9e19-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="b9e19-110">Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="b9e19-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="b9e19-111">Однако следует отметить, что отключение соединители для группы Microsoft 365, от которую зависит рабочая группа, также отключит возможность создавать соединители для этой группы.</span><span class="sxs-lookup"><span data-stu-id="b9e19-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="b9e19-112">Соединитетели по умолчанию отключены в средах Community (GCC) для государственных GCC.</span><span class="sxs-lookup"><span data-stu-id="b9e19-112">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="b9e19-113">Если вам нужно включить их, задайте для параметров ConnectorsEnabled или ConnectorsEnabledForTeams $true с помощью $true [SetOrganizationConfig.](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="b9e19-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="b9e19-114">Раньше вам требовалось подключиться к [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="b9e19-114">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="b9e19-115">Добавление соединителю в канал</span><span class="sxs-lookup"><span data-stu-id="b9e19-115">Add a connector to a channel</span></span>

<span data-ttu-id="b9e19-116">В настоящее время вы можете добавлять соединители с помощью Microsoft Teams и веб-клиентов.</span><span class="sxs-lookup"><span data-stu-id="b9e19-116">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="b9e19-117">Однако информацию, опубликованную этими соединителами, можно просмотреть во всех **клиентах,** включая мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="b9e19-117">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="b9e19-118">Чтобы добавить соединитель в канал, щелкните многострок **(...),** справа от имени канала, а затем выберите **Соединители**.</span><span class="sxs-lookup"><span data-stu-id="b9e19-118">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9e19-119">![Снимок экрана: Teams с выбранным параметром "Соединитетели".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-119">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="b9e19-120">Вы можете выбрать один из множества доступных соединитетелей и нажать кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b9e19-120">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9e19-121">![Снимок экрана: диалоговое окно "Соединитетели", в котором показаны доступные соединители.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-121">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="b9e19-122">Укажите требуемые данные о соединителе и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b9e19-122">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="b9e19-123">Для правильной работы соединителям требуется самая разнообразная информация, а некоторым — еще и вход пользователя в службу по ссылкам на странице конфигурации соединителя.</span><span class="sxs-lookup"><span data-stu-id="b9e19-123">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9e19-124">![Снимок экрана страницы конфигурации для соединителя RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-124">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="b9e19-125">Предоставляемые соединителем данные автоматически публикуются в канале.</span><span class="sxs-lookup"><span data-stu-id="b9e19-125">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9e19-126">![Снимок экрана интерфейса Teams с беседой в канале.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-126">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="b9e19-127">**Уведомление об обновлении URL-адреса соединителя**</span><span class="sxs-lookup"><span data-stu-id="b9e19-127">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="b9e19-128">Соедините Teams переходят на новый URL-адрес для повышения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b9e19-128">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="b9e19-129">В ходе этого перехода вы будете получать определенные уведомления об обновлении настроенного соединитела для использования нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b9e19-129">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="b9e19-130">Настоятельно рекомендуется немедленно обновить соединители, чтобы избежать перебоев в работе соединитеных служб.</span><span class="sxs-lookup"><span data-stu-id="b9e19-130">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="b9e19-131">Чтобы обновить URL-адрес, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b9e19-131">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="b9e19-132">На странице конфигурации соединители под кнопкой "Управление" отобразилось сообщение "Требуется внимание" для подключений, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="b9e19-132">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="b9e19-133">![Снимок экрана: сообщение "Требуется внимание".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-133">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="b9e19-134">Для соединителя входящих веб-страниц пользователи могут повторно создать подключение, просто выбрав Обновить **URL-адрес** и используя только что созданный URL-адрес веб-канала.</span><span class="sxs-lookup"><span data-stu-id="b9e19-134">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="b9e19-135">![Снимок экрана: кнопка "Обновить URL-адрес".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-135">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="b9e19-136">Для других типов соединитегорий пользователю потребуется удалить соединитегорию и повторно создать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b9e19-136">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="b9e19-137">После успешного обновления URL-адреса вы увидите сообщение "URL-адрес обновлен".</span><span class="sxs-lookup"><span data-stu-id="b9e19-137">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="b9e19-138">![Снимок экрана: сообщение "URL-адрес является последние".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="b9e19-138">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="b9e19-139">Разработка настраиваемых соединителей</span><span class="sxs-lookup"><span data-stu-id="b9e19-139">Develop custom connectors</span></span>


<span data-ttu-id="b9e19-140">Вы также можете создавать пользовательские соединители, а также входящие и исходяющие веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="b9e19-140">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="b9e19-141">Дополнительные сведения см. в [документации для разработчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="b9e19-141">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
