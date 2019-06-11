---
title: 'Lync Server 2013: вход в виртуальную машину и использование на ней Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="62278-102">Вход в виртуальную машину и использование на ней Lync 2013</span><span class="sxs-lookup"><span data-stu-id="62278-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62278-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="62278-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="62278-104">После включения надстройки VDI выполняются описанные ниже действия, когда пользователь входит в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="62278-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="62278-105">Пользователь вводит свои учетные данные в клиент Lync 2013, работающий на виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="62278-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="62278-106">После того как Lync обнаружит доступность плагина VDI, Lync предложит пользователю повторно ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="62278-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="62278-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span><span class="sxs-lookup"><span data-stu-id="62278-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="62278-108">Lync начинает связывание с помощью плагина VDI.</span><span class="sxs-lookup"><span data-stu-id="62278-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="62278-109">Перед завершением связывания клиент отображает в строке состояния Lync два значка.</span><span class="sxs-lookup"><span data-stu-id="62278-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="62278-110">Значок внизу слева указывает на то, что звуковое устройство недоступно, а значок мигания справа внизу указывает на то, что связывание VDI выполняется, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="62278-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="62278-111">![Значок LYNC VDI] , показывающий успешное связывание (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Значок LYNC VDI") , показывающий успешное связывание</span><span class="sxs-lookup"><span data-stu-id="62278-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="62278-112">После успешного сопряжения подключаемого модуля VDI значки изменяются и теперь обозначают аудиоустройство, которое будет использоваться для выполнения вызовов, а также успешное сопряжение VDI:</span><span class="sxs-lookup"><span data-stu-id="62278-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="62278-113">![Значок связывания в LYNC VDI] , демонстрирующий успешное создание (images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Значок связывания в LYNC VDI") , демонстрирующий успешное создание</span><span class="sxs-lookup"><span data-stu-id="62278-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="62278-114">После пар Lync с подключаемым модулем VDI пользователь может видеть свое присутствие на устройствах, совместимых с Lync, которые подключены к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="62278-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="62278-115">Теперь пользователь может размещать и отвечать на звонки в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="62278-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

