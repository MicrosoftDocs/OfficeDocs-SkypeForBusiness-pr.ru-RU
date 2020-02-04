---
title: 'Lync Server 2013: замена Ксмладаптер с настроенным адаптером соответствия для сервера сохраняемого чата'
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
ms.openlocfilehash: 9235c57a055131049251d17b75f73a4370cc5f2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="3b4fb-102">Замена Ксмладаптер с помощью настроенного адаптера соответствия требованиям сервера для подключения к серверу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b4fb-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b4fb-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b4fb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3b4fb-104">Вы можете написать собственный адаптер, вместо того чтобы использовать Ксмладаптер, установленный на сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="3b4fb-105">Для этого необходимо предоставить сборку .NET Framework, которая содержит общий класс, реализующий интерфейс **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="3b4fb-106">Эту сборку необходимо поместить в папку установки сервера сохраняемого чата для каждого сервера в пуле сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="3b4fb-107">Данные проверки совместимости могут поступать в адаптер с любого сервера проверки совместимости, но на разные экземпляры адаптера с серверов проверки совместимости на поступают повторяющиеся данные.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="3b4fb-108">Реализация интерфейса Икомплианцеадаптер</span><span class="sxs-lookup"><span data-stu-id="3b4fb-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="3b4fb-109">Интерфейс определен в сборке соответствие. dll в пространстве имен `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="3b4fb-110">Интерфейс определяет два метода, которые должен реализовать пользовательский адаптер.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="3b4fb-111">Этот метод будет вызываться при первой загрузке адаптера с помощью постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="3b4fb-112">`AdapterConfig` Содержит постоянную конфигурацию соответствия чатов, связанную с адаптером соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="3b4fb-113">Сервер соответствия требованиям в чате вызывает этот метод через определенные интервалы времени, пока для перевода не поступило новых данных.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="3b4fb-114">Этот интервал времени равен значению, `RunInterval` заданному в параметрах соответствия требованиям сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="3b4fb-115">`ConversationCollection` Содержит сведения о разговоре, собранные с момента последнего вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="3b4fb-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

