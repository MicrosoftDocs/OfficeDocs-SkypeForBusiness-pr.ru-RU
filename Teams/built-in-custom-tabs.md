---
title: "Использование встроенных и настраиваемых вкладок в Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения об использовании встроенных и настраиваемых вкладок для таких компонентов, как беседы, файлы, карты и многое другое."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2ba0e5d8897b7c77aa4fd9c319c9a77fcf2129b9
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="6c391-103">Использование встроенных и настраиваемых вкладок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c391-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="6c391-104">Благодаря вкладкам участники команды получают доступ к службам на выделенном холсте внутри канала.</span><span class="sxs-lookup"><span data-stu-id="6c391-104">Tabs allow team members to access services on a dedicated canvas within a channel.</span></span> <span data-ttu-id="6c391-105">Это позволяет команде напрямую работать с предоставляемыми вами средствами и данными, а также обсуждать их в контексте канала.</span><span class="sxs-lookup"><span data-stu-id="6c391-105">This lets the team work directly with the tools and data you provide, and to have conversations about them, in the channel’s context.</span></span> <span data-ttu-id="6c391-106">По умолчанию каждый новый канал имеет две вкладки, как показано на следующем изображении:</span><span class="sxs-lookup"><span data-stu-id="6c391-106">With every new channel, two tabs are provisioned by default, as listed and shown in the image, below:</span></span>

-   <span data-ttu-id="6c391-107">Беседы</span><span class="sxs-lookup"><span data-stu-id="6c391-107">Conversations</span></span>

-   <span data-ttu-id="6c391-108">Файлы</span><span class="sxs-lookup"><span data-stu-id="6c391-108">Files</span></span>

![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)

1.  <span data-ttu-id="6c391-109">Владельцы и участники команды могут добавлять в каждый из каналов дополнительные вкладки для интеграции с соответствующими облачными службами.</span><span class="sxs-lookup"><span data-stu-id="6c391-109">Owners and team members can add additional tabs, to each channel, to help integrate their cloud services.</span></span>

2.  <span data-ttu-id="6c391-110">Для преобразования во вкладки файлы Excel, PowerPoint, Word и PDF нужно отправить на **вкладку "Файлы"**.</span><span class="sxs-lookup"><span data-stu-id="6c391-110">Excel, PowerPoint, Word and PDF files must be uploaded to the **Files tab** before they can be converted to tabs.</span></span> <span data-ttu-id="6c391-111">Кроме того, уже отправленные файлы можно преобразовать во вкладки одним щелчком мыши, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6c391-111">Alternatively, any existing uploaded, files can be converted into tabs with a single click, as shown below.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="6c391-112">Чтобы добавить веб-сайт, его URL-адрес должен начинаться с **префикса https**, так как это обеспечивает безопасность при обмене данными.</span><span class="sxs-lookup"><span data-stu-id="6c391-112">To add a website, the URL must start with an **https prefix,** so that any information exchanged remains secure.</span></span>

4.  <span data-ttu-id="6c391-113">Если участник команды пытается добавить в канал настраиваемую вкладку, то получает подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="6c391-113">Detailed instructions are provided when a team member attempts to add a custom tab into their channel.</span></span>

5.  <span data-ttu-id="6c391-114">После добавления настраиваемой вкладки в канал создается **вкладка "Беседа"**, где участники команды могут обсудить данный контент.</span><span class="sxs-lookup"><span data-stu-id="6c391-114">When a Custom tab is added into a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

6.  <span data-ttu-id="6c391-115">В каналы можно добавлять дополнительные вкладки, чтобы помочь пользователям обращаться к нужным данным и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="6c391-115">Additional tabs can be added to channels to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="6c391-116">Это может быть отчет Power BI, панель мониторинга и даже видеоканал [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785), где вы публикуете обучающие ролики.</span><span class="sxs-lookup"><span data-stu-id="6c391-116">This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

<a name="develop-custom-tabs"></a><span data-ttu-id="6c391-117">Разработка настраиваемых вкладок</span><span class="sxs-lookup"><span data-stu-id="6c391-117">Develop custom tabs</span></span>
-------------------

<span data-ttu-id="6c391-118">Кроме встроенных вкладок, организации могут легко разрабатывать и проектировать свои собственные вкладки, которые можно интегрировать с Microsoft Teams или предоставить сообществу.</span><span class="sxs-lookup"><span data-stu-id="6c391-118">In addition to the built-in tabs, organizations can easily design and develop their own tabs, that can be integrated into Microsoft Teams, or shared with the rest of the community.</span></span>

<span data-ttu-id="6c391-119">Microsoft Developer Network содержит [подробные инструкции](https://go.microsoft.com/fwlink/?linkid=855786) по проектированию и разработке собственных вкладок, кроме того, можно скачать и развернуть [примеры вкладок](https://go.microsoft.com/fwlink/?linkid=855787) от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6c391-119">The Microsoft Developer Network provides [detailed instructions](https://go.microsoft.com/fwlink/?linkid=855786) to design and build your own tabs; and download and deploy [sample tabs](https://go.microsoft.com/fwlink/?linkid=855787) developed by Microsoft.</span></span>

![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)
