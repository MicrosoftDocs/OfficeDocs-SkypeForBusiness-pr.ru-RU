---
title: Использование Office 365 и настраиваемых соединителей в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Соединители предоставляют команде актуальные сведения и данные из часто используемых служб, передавая их прямо в канал.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245210"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="4480d-103">Использование Office 365 и настраиваемых соединителей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4480d-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="4480d-104">Соединительные линии своевременно заставляют вашу команду за счет часто используемых обновлений контента и служб прямо в канале.</span><span class="sxs-lookup"><span data-stu-id="4480d-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="4480d-105">С помощью соединителей пользователи Microsoft Teams смогут получать обновления из популярных служб, таких как Twitter, Trello, Wunderlist, GitHub и Azure Девопс, в потоке чата в их команде.</span><span class="sxs-lookup"><span data-stu-id="4480d-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="4480d-106">Любой участник команды может подключить свою команду к популярным облачным службам с соединителями, если разрешены разрешения для группы, и все участники группы уведомлены о действиях, выполняемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="4480d-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="4480d-107">Соединительные линии будут продолжать работать даже после того, как пользователь, который их первоначально найдет, оставил.</span><span class="sxs-lookup"><span data-stu-id="4480d-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="4480d-108">Любой участник группы с разрешениями на разрешение на присоединение может изменять настройку соединителей другими участниками.</span><span class="sxs-lookup"><span data-stu-id="4480d-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="4480d-109">Соединители Office 365 можно использовать как для Microsoft Teams, так и для групп Office 365, что помогает всем участникам получать актуальную информацию.</span><span class="sxs-lookup"><span data-stu-id="4480d-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="4480d-110">Microsoft Teams и Exchange используют одинаковую модель соединителей, что позволяет использовать одни соединители на обеих платформах.</span><span class="sxs-lookup"><span data-stu-id="4480d-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="4480d-111">Однако стоит заметить, что при отключении соединителей для группы Office 365, от которой зависит группа, будет запрещено создавать соединители для этой группы.</span><span class="sxs-lookup"><span data-stu-id="4480d-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="4480d-112">Добавление соединительной линии в канал</span><span class="sxs-lookup"><span data-stu-id="4480d-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="4480d-113">В настоящее время вы можете добавлять соединители с помощью классических и веб-клиентов Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4480d-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="4480d-114">Однако данные, опубликованные этими соединителями, можно просматривать на **всех клиентах** , включая мобильный.</span><span class="sxs-lookup"><span data-stu-id="4480d-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="4480d-115">Чтобы добавить соединительную линию в канал, щелкните **многоточие (...)** справа от имени канала и выберите пункт **соединители**.</span><span class="sxs-lookup"><span data-stu-id="4480d-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Снимок экрана: интерфейс Teams с выбранным параметром "соединители".](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="4480d-117">Вы можете выбрать один из доступных соединителей, а затем нажать кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4480d-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Снимок экрана: диалоговое окно "соединители", показывающее Доступные соединительные линии.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="4480d-119">Укажите требуемые данные о соединителе и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4480d-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="4480d-120">Для правильной работы соединителям требуется самая разнообразная информация, а некоторым — еще и вход пользователя в службу по ссылкам на странице конфигурации соединителя.</span><span class="sxs-lookup"><span data-stu-id="4480d-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Снимок экрана страницы конфигурации для соединителя RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="4480d-122">Предоставляемые соединителем данные автоматически публикуются в канале.</span><span class="sxs-lookup"><span data-stu-id="4480d-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Снимок экрана интерфейса Teams с беседой в канале.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="4480d-124">Разработка настраиваемых соединителей</span><span class="sxs-lookup"><span data-stu-id="4480d-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="4480d-125">Создавать собственные соединители, которые можно интегрировать с бизнес-приложениями, очень просто.</span><span class="sxs-lookup"><span data-stu-id="4480d-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="4480d-126">Для создания конечной точки канала, который получает данные из любого приложения, использующего HTTP-методы POST, вы можете использовать встроенную соединительную линию **входящего веб** -перехватчика.</span><span class="sxs-lookup"><span data-stu-id="4480d-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="4480d-127">**Incoming Webhook** добавляется аналогично любому другому соединителю.</span><span class="sxs-lookup"><span data-stu-id="4480d-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Снимок экрана с параметром для добавления соединителя "Incoming Webhook" (Веб-перехватчик входящего трафика).](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="4480d-129">Чтобы создать веб-перехватчик, укажите **имя**, при необходимости обновите изображение веб-перехватчика, а затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4480d-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Снимок экрана: страница конфигурации для соединителя входящих веб-перехватчиков.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="4480d-131">Приложения, передающие данные на этот канал, требуют URL-адреса соединителя веб-перехватчика.</span><span class="sxs-lookup"><span data-stu-id="4480d-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="4480d-132">При создании веб-перехватчика создается уникальный адрес URL.</span><span class="sxs-lookup"><span data-stu-id="4480d-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="4480d-133">Поделитесь этим URL-адресом с разработчиками, чтобы они могли настроить приложения для отправки данных по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="4480d-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Снимок экрана с уникальным URL-адресом веб-перехватчика.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="4480d-135">Когда внешнее приложение передает данные соединителю, в списке бесед канала отображается специальное сообщение, называемое **карточкой соединителя**.</span><span class="sxs-lookup"><span data-stu-id="4480d-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Снимок экрана интерфейса Teams с сообщением карточки соединителя.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="4480d-137">Разработчики могут настроить приложения для создания этих карточек, отправив запрос HTTP с простым набором полезных данных JSON в адрес веб-перехватчика команды, который является уникальным URL-адресом конечной точки, предоставленной мастером.</span><span class="sxs-lookup"><span data-stu-id="4480d-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="4480d-138">Попросите разработчиков обратиться к разделу [Начало работы с соединителями Office 365 для Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)в сети разработчиков Майкрософт, содержащей подробные инструкции и примеры соединителей.</span><span class="sxs-lookup"><span data-stu-id="4480d-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="4480d-139">Кроме того, к полезным ресурсам относится статья [Подключение приложений к группам в Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) и раздел о [Microsoft Teams в Центре разработки для Office](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="4480d-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
