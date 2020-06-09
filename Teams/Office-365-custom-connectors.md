---
title: Использование Microsoft 365 и настраиваемых соединителей
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 9ea72fbe054e3a6d0e89f87f1a8c23303ef55c5c
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637758"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="af5b7-103">Использование Microsoft 365 и настраиваемых соединителей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af5b7-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="af5b7-104">Соединительные линии своевременно заставляют вашу команду за счет часто используемых обновлений контента и служб прямо в канале.</span><span class="sxs-lookup"><span data-stu-id="af5b7-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="af5b7-105">С помощью соединителей пользователи Microsoft Teams смогут получать обновления из популярных служб, таких как Twitter, Trello, Wunderlist, GitHub и Azure DevOps, в потоке чата в их команде.</span><span class="sxs-lookup"><span data-stu-id="af5b7-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="af5b7-106">Любой участник команды может подключить свою команду к популярным облачным службам с соединителями, если разрешены разрешения для группы, и все участники группы уведомлены о действиях, выполняемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="af5b7-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="af5b7-107">Соединительные линии будут продолжать работать даже после того, как пользователь, который их первоначально найдет, оставил.</span><span class="sxs-lookup"><span data-stu-id="af5b7-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="af5b7-108">Любой участник группы с разрешениями на разрешение на присоединение может изменять настройку соединителей другими участниками.</span><span class="sxs-lookup"><span data-stu-id="af5b7-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="af5b7-109">Соединители Microsoft 365 можно использовать с группами Microsoft Teams и Microsoft 365, что упрощает синхронизацию и своевременную получение важной информации.</span><span class="sxs-lookup"><span data-stu-id="af5b7-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="af5b7-110">Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="af5b7-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="af5b7-111">Однако стоит отметить, что отключение соединителей для группы Microsoft 365, от которой зависит группа, будет отключаться также от возможности создания соединителей для этой группы.</span><span class="sxs-lookup"><span data-stu-id="af5b7-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="af5b7-112">Добавление соединительной линии в канал</span><span class="sxs-lookup"><span data-stu-id="af5b7-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="af5b7-113">В настоящее время вы можете добавлять соединители с помощью классических и веб-клиентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af5b7-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="af5b7-114">Однако данные, опубликованные этими соединителями, можно просматривать на **всех клиентах** , включая мобильный.</span><span class="sxs-lookup"><span data-stu-id="af5b7-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="af5b7-115">Чтобы добавить соединительную линию в канал, щелкните **многоточие (...)** справа от имени канала и выберите пункт **соединители**.</span><span class="sxs-lookup"><span data-stu-id="af5b7-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Снимок экрана: интерфейс Teams с выбранным параметром "соединители".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="af5b7-117">Вы можете выбрать один из доступных соединителей, а затем нажать кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="af5b7-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Снимок экрана: диалоговое окно "соединители", показывающее Доступные соединительные линии.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="af5b7-119">Укажите требуемые данные о соединителе и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af5b7-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="af5b7-120">Для правильной работы соединителям требуется самая разнообразная информация, а некоторым — еще и вход пользователя в службу по ссылкам на странице конфигурации соединителя.</span><span class="sxs-lookup"><span data-stu-id="af5b7-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Снимок экрана страницы конфигурации для соединителя RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="af5b7-122">Предоставляемые соединителем данные автоматически публикуются в канале.</span><span class="sxs-lookup"><span data-stu-id="af5b7-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Снимок экрана интерфейса Teams с беседой в канале.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="af5b7-124">Разработка настраиваемых соединителей</span><span class="sxs-lookup"><span data-stu-id="af5b7-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="af5b7-125">Вы также можете создавать пользовательские соединители, а также входящие и исходящие веб-перехватчики.</span><span class="sxs-lookup"><span data-stu-id="af5b7-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="af5b7-126">Дополнительные сведения см. в [документации для разработчиков](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="af5b7-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
