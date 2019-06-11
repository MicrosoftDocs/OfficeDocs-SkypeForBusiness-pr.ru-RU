---
title: 'Lync Server 2013: Примечание о Lync – подключение к Skype для Lync на'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3c3327a731f3a7c6bba25469376ffffeee8d8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="20ba8-102">Примечание о соединении Lync — Skype в Lync Server 2013 для пользователей Lync Online</span><span class="sxs-lookup"><span data-stu-id="20ba8-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20ba8-103">_**Тема последнего изменения:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="20ba8-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="20ba8-104">Этот документ предназначен для того, чтобы помочь администраторам локального сервера Lync Server настроить Lync – подключение к Skype.</span><span class="sxs-lookup"><span data-stu-id="20ba8-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="20ba8-105">Lync – подключение к Skype также является функцией Lync Online, которая входит в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="20ba8-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="20ba8-106">Вы можете включить функцию подключения Lync-Skype из центра администрирования Lync на портале Office 365.</span><span class="sxs-lookup"><span data-stu-id="20ba8-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Office 365 portal.</span></span>

<span data-ttu-id="20ba8-107">Для Office 365 среднего бизнеса, Office 365 корпоративный, Office 365 для образовательных учреждений и Office 365 для государственных организаций: Войдите на портал Office 365 и перейдите в **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="20ba8-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="20ba8-108">Переход на **внешнюю связь**.</span><span class="sxs-lookup"><span data-stu-id="20ba8-108">Go to **External Communications**.</span></span> <span data-ttu-id="20ba8-109">В разделе **поставщики общедоступной службы обмена мгновенными сообщениями**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="20ba8-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="20ba8-110">Если вы хотите контролировать доступ отдельных пользователей к Lync – подключение к Skype, вы можете сделать это, изменив параметры внешних подключений отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="20ba8-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="20ba8-111">Для Office 365 для малого бизнеса расширенный: Войдите в Office 365 и перейдите к разделу **Настройка \> \> службы администрирования мгновенных сообщений, собраний и конференций**.</span><span class="sxs-lookup"><span data-stu-id="20ba8-111">For Office 365 Small Business Premium: Sign in to Office 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="20ba8-112">Включите функцию внешней связи.</span><span class="sxs-lookup"><span data-stu-id="20ba8-112">Turn on External communications.</span></span> <span data-ttu-id="20ba8-113">Коммутатор внешней связи включает в себя связь Lync — Skype и связь с другими организациями, которые используют Lync.</span><span class="sxs-lookup"><span data-stu-id="20ba8-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="20ba8-114">В зависимости от того, когда вы начали пользоваться Lync Online, в состоянии "вкл." внешнем переключателе связи может быть указано только то, что активирована связь с другими организациями Lync.</span><span class="sxs-lookup"><span data-stu-id="20ba8-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="20ba8-115">Чтобы включить функцию Lync – подключение к Skype, просто переключите флажок и снова включите ее.</span><span class="sxs-lookup"><span data-stu-id="20ba8-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

