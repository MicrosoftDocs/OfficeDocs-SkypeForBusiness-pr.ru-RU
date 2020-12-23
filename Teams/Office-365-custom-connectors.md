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
ms.openlocfilehash: 3b7847ce2aba9a155622e83a6c0449cc1b6b1a39
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177219"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="509ca-103">Использование Microsoft 365 и настраиваемые соединители в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="509ca-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="509ca-104">Соединители обеспечивают обновляемую информацию для группы, доставляя часто используемое содержимое и обновления служб непосредственно в канал.</span><span class="sxs-lookup"><span data-stu-id="509ca-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="509ca-105">Благодаря соединителям пользователи Microsoft Teams могут получать обновления из популярных служб, таких как Trello, Wunderlist, GitHub и Службы Azure DevOps, в потоке чата своей команды.</span><span class="sxs-lookup"><span data-stu-id="509ca-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="509ca-106">Любой участник команды может связать свою команду с популярными облачными службами с помощью соединитеров, если это допускается разрешениями группы, и все участники группы будут уведомлены о действиях в этой службе.</span><span class="sxs-lookup"><span data-stu-id="509ca-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="509ca-107">Соединитетели продолжат работать даже после того, как участник, изначально настроивший соединителю, покинул ее.</span><span class="sxs-lookup"><span data-stu-id="509ca-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="509ca-108">Любой участник группы с разрешениями на добавление и удаление может изменять соединители, которые настроены другими участниками.</span><span class="sxs-lookup"><span data-stu-id="509ca-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="509ca-109">Соединители Microsoft 365 можно использовать как с Группами Microsoft Teams, так и с Microsoft 365, чтобы всем участникам было проще синхронизироваться и быстро получать важные сведения.</span><span class="sxs-lookup"><span data-stu-id="509ca-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="509ca-110">Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="509ca-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="509ca-111">Однако следует отметить, что отключение соединители для группы Microsoft 365, от которую зависит рабочая группа, также отключит для нее возможность создавать соединители.</span><span class="sxs-lookup"><span data-stu-id="509ca-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="509ca-112">Добавление соединителю в канал</span><span class="sxs-lookup"><span data-stu-id="509ca-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="509ca-113">В настоящее время вы можете добавлять соединители с помощью классических и веб-клиентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="509ca-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="509ca-114">Однако информацию, опубликованную этими соединиттелями, можно просмотреть во **всех** клиентах, включая мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="509ca-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="509ca-115">Чтобы добавить соединитель в канал, щелкните **многоellips (...),** справа от имени канала, а затем выберите **"Соединители".**</span><span class="sxs-lookup"><span data-stu-id="509ca-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="509ca-116">![Снимок экрана: интерфейс Teams с выбранным параметром "Соединители".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="509ca-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="509ca-117">Вы можете выбрать соединители из множества доступных, а затем нажать кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="509ca-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="509ca-118">![Снимок экрана: диалоговое окно "Соединитетели", в котором показаны доступные соединители.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="509ca-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="509ca-119">Укажите требуемые данные о соединителе и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="509ca-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="509ca-120">Для правильной работы соединителям требуется самая разнообразная информация, а некоторым — еще и вход пользователя в службу по ссылкам на странице конфигурации соединителя.</span><span class="sxs-lookup"><span data-stu-id="509ca-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="509ca-121">![Снимок экрана страницы конфигурации для соединителя RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="509ca-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="509ca-122">Предоставляемые соединителем данные автоматически публикуются в канале.</span><span class="sxs-lookup"><span data-stu-id="509ca-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="509ca-123">![Снимок экрана интерфейса Teams с беседой в канале.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="509ca-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<a name="develop-custom-connectors"></a><span data-ttu-id="509ca-124">Разработка настраиваемых соединителей</span><span class="sxs-lookup"><span data-stu-id="509ca-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="509ca-125">Вы также можете создавать пользовательские соединители, а также входящие и исходящую веб-службы.</span><span class="sxs-lookup"><span data-stu-id="509ca-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="509ca-126">Дополнительные сведения см. в [документации для разработчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="509ca-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
