---
title: Использование Microsoft 365 и настраиваемые соединители
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
description: Соединители предоставляют команде актуальные сведения и данные из часто используемых служб, передавая их прямо в канал.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076421"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="af6f2-103">Использование Microsoft 365 и настраиваемые соединители в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af6f2-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="af6f2-104">Соединители обеспечивают обновляемую информацию для группы, доставляя часто используемое содержимое и обновления служб непосредственно в канал.</span><span class="sxs-lookup"><span data-stu-id="af6f2-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="af6f2-105">Благодаря соединителям пользователи Microsoft Teams могут получать обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Службы Azure DevOps, в потоке чата своей команды.</span><span class="sxs-lookup"><span data-stu-id="af6f2-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="af6f2-106">Любой участник команды может связать свою команду с популярными облачными службами с помощью соединитеров, если это допускается разрешениями группы, и все участники группы будут уведомлены о действиях в этой службе.</span><span class="sxs-lookup"><span data-stu-id="af6f2-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="af6f2-107">Соединитетели продолжат работать даже после того, как участник, изначально настроивший соединителю, покинул ее.</span><span class="sxs-lookup"><span data-stu-id="af6f2-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="af6f2-108">Любой участник группы с разрешениями на добавление и удаление может изменять соединители, которые настроены другими участниками.</span><span class="sxs-lookup"><span data-stu-id="af6f2-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="af6f2-109">Соединители Microsoft 365 можно использовать как с Группами Microsoft Teams, так и с Microsoft 365, чтобы всем участникам было проще синхронизироваться и быстро получать важные сведения.</span><span class="sxs-lookup"><span data-stu-id="af6f2-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="af6f2-110">Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="af6f2-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="af6f2-111">Однако следует отметить, что отключение соединители для группы Microsoft 365, от которую зависит рабочая группа, также отключит для нее возможность создавать соединители.</span><span class="sxs-lookup"><span data-stu-id="af6f2-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="af6f2-112">Добавление соединителю в канал</span><span class="sxs-lookup"><span data-stu-id="af6f2-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="af6f2-113">В настоящее время вы можете добавлять соединители с помощью классических и веб-клиентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af6f2-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="af6f2-114">Однако информацию, опубликованную этими соединиттелями, можно просмотреть во **всех** клиентах, включая мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="af6f2-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="af6f2-115">Чтобы добавить соединитель в канал, щелкните **многоellips (...),** справа от имени канала, а затем выберите **"Соединители".**</span><span class="sxs-lookup"><span data-stu-id="af6f2-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af6f2-116">![Снимок экрана: интерфейс Teams с выбранным параметром "Соединители".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="af6f2-117">Вы можете выбрать соединители из множества доступных, а затем нажать кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="af6f2-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af6f2-118">![Снимок экрана: диалоговое окно "Соединитетели", в котором показаны доступные соединители.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="af6f2-119">Укажите требуемые данные о соединителе и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af6f2-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="af6f2-120">Для правильной работы соединителям требуется самая разнообразная информация, а некоторым — еще и вход пользователя в службу по ссылкам на странице конфигурации соединителя.</span><span class="sxs-lookup"><span data-stu-id="af6f2-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af6f2-121">![Снимок экрана страницы конфигурации для соединителя RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="af6f2-122">Предоставляемые соединителем данные автоматически публикуются в канале.</span><span class="sxs-lookup"><span data-stu-id="af6f2-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="af6f2-123">![Снимок экрана интерфейса Teams с беседой в канале.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="af6f2-124">**Уведомление об обновлении URL-адреса соединителя**</span><span class="sxs-lookup"><span data-stu-id="af6f2-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="af6f2-125">Соединители Teams переходят на новый URL-адрес для повышения безопасности.</span><span class="sxs-lookup"><span data-stu-id="af6f2-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="af6f2-126">В ходе этого перехода вы будете получать определенные уведомления об обновлении настроенного соединителя для использования нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="af6f2-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="af6f2-127">Настоятельно рекомендуется немедленно обновить соединители, чтобы предотвратить прерывать подключение к соединители службам.</span><span class="sxs-lookup"><span data-stu-id="af6f2-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="af6f2-128">Чтобы обновить URL-адрес, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="af6f2-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="af6f2-129">На странице конфигурации соединитеителей под кнопкой "Управление" для подключений, которые необходимо обновить, отобразилось сообщение "Требуется внимание".</span><span class="sxs-lookup"><span data-stu-id="af6f2-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="af6f2-130">![Снимок экрана: сообщение "Требуется внимание".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="af6f2-131">При входящих соединителях webhook пользователи могут  воссоздать подключение, просто выбрав "Обновить URL-адрес" и используя только что созданный URL-адрес веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="af6f2-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="af6f2-132">![Снимок экрана: кнопка "Обновить URL-адрес".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="af6f2-133">Для других типов соединитегорий пользователю потребуется удалить соедините отчетность и воссоздать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="af6f2-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="af6f2-134">После успешного обновления URL-адреса вы увидите сообщение "URL-адрес обновлен".</span><span class="sxs-lookup"><span data-stu-id="af6f2-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="af6f2-135">![Снимок экрана: сообщение "URL-адрес является последние".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="af6f2-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="af6f2-136">Разработка настраиваемых соединителей</span><span class="sxs-lookup"><span data-stu-id="af6f2-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="af6f2-137">Вы также можете создавать пользовательские соединители, а также входящие и исходящую веб-службы.</span><span class="sxs-lookup"><span data-stu-id="af6f2-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="af6f2-138">Дополнительные сведения см. в [документации для разработчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="af6f2-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
