---
title: 'Lync Server 2013: Примечание о подключении к Lync-Skype для Lync в'
description: 'Lync Server 2013: Примечание о подключении к Lync-Skype для Lync on.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7d9758f277f2f987677c2c0ffa0a4447ba31d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579205"
---
# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="32514-103">Примечание о подключении к Lync-Skype в Lync Server 2013 для клиентов Lync Online</span><span class="sxs-lookup"><span data-stu-id="32514-103">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32514-104">_**Последнее изменение темы:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="32514-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="32514-105">Этот документ был написан, чтобы помочь локальным администраторам Lync Server настраивать Lync-Skype подключения.</span><span class="sxs-lookup"><span data-stu-id="32514-105">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="32514-106">Lync-Skype возможность подключения также является компонентом Lync Online, который входит в состав Office 365 и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32514-106">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365 and Microsoft 365.</span></span> <span data-ttu-id="32514-107">Функцию подключения к Lync-Skype можно включить в центре администрирования Lync в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="32514-107">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the admin center.</span></span>

<span data-ttu-id="32514-108">Для Microsoft 365 среднего бизнеса, Office 365 корпоративный, Microsoft 365 для образовательных учреждений и Office 365 для государственных учреждений: Войдите на портал Office 365 или центр администрирования Microsoft 365 и перейдите в **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="32514-108">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Office 365 portal or Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="32514-109">Перейдите к разделу **Внешние коммуникации**.</span><span class="sxs-lookup"><span data-stu-id="32514-109">Go to **External Communications**.</span></span> <span data-ttu-id="32514-110">В разделе **поставщики общедоступных служб обмена мгновенными сообщениями**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="32514-110">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="32514-111">Если требуется управлять доступом отдельных пользователей к Lync-Skype подключениям, можно изменить параметры внешнего взаимодействия отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="32514-111">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="32514-112">Для Microsoft 365 малый бизнес расширенный: Войдите в Microsoft 365 и перейдите к разделу \*\* \> Настройка службы администрирования \> Обмен мгновенными сообщениями, собрания и конференц\*\*-связи.</span><span class="sxs-lookup"><span data-stu-id="32514-112">For Microsoft 365 Small Business Premium: Sign in to Microsoft 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="32514-113">Включите внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="32514-113">Turn on External communications.</span></span> <span data-ttu-id="32514-114">Внешний коммутатор связи включает Lync-Skype подключения и связи с другими организациями, использующими Lync.</span><span class="sxs-lookup"><span data-stu-id="32514-114">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="32514-115">В зависимости от того, когда вы начали использовать Lync Online, внешний коммутатор связи в состоянии "вкл." может первоначально указывать только на то, что активируется связь с другими организациями Lync.</span><span class="sxs-lookup"><span data-stu-id="32514-115">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="32514-116">Чтобы включить Lync-Skype подключения, просто переключите его и снова включите снова.</span><span class="sxs-lookup"><span data-stu-id="32514-116">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

