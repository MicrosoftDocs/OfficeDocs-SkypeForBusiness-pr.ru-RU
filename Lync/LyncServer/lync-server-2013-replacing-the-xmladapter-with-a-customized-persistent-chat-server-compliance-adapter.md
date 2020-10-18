---
title: 'Lync Server 2013: замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата'
description: 'Lync Server 2013: замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576145"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="9dc6e-103">Замена Ксмладаптер на настраиваемый адаптер соответствия сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dc6e-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc6e-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9dc6e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9dc6e-105">Вы можете написать настраиваемый адаптер вместо использования Ксмладаптер, установленного с сервером сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="9dc6e-106">Для этого необходимо предоставить сборку .NET Framework, содержащую общий класс, который реализует интерфейс **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="9dc6e-107">Эту сборку необходимо поместить в папку установки сервера сохраняемого чата на каждом сервере в пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="9dc6e-108">Любой из серверов совместимости может предоставлять данные о совместимости адаптеру, но серверы совместимости не могут предоставлять дублированные данные о совместимости нескольким экземплярам адаптера.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="9dc6e-109">Реализация интерфейса Икомплианцеадаптер</span><span class="sxs-lookup"><span data-stu-id="9dc6e-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="9dc6e-110">Интерфейс определяется в сборке Compliance.dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="9dc6e-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="9dc6e-111">В интерфейсе определены два метода, которые должен реализовать настраиваемый адаптер.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="9dc6e-112">Сервер соответствия сохраняемого чата будет вызывать этот метод при первой загрузке адаптера.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="9dc6e-113">`AdapterConfig`Содержит конфигурацию соответствия сохраняемого чата, относящуюся к адаптеру соответствия.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="9dc6e-114">Сервер соответствия сохраняемого чата вызывает этот метод через определенные интервалы времени до тех пор, пока не переводятся новые данные.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="9dc6e-115">Этот интервал времени равен значению, заданному `RunInterval` в настройках соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="9dc6e-116">`ConversationCollection`Содержит сведения о беседе, собранные при последнем вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="9dc6e-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

