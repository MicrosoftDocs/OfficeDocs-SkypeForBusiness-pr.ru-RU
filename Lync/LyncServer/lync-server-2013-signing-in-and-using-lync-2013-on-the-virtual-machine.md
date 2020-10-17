---
title: 'Lync Server 2013: вход и использование Lync 2013 на виртуальной машине'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710119091a5ed6254f18f7b40a4549ab9d09c776
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533986"
---
# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="139ff-102">Вход на виртуальную машину и использование Lync 2013</span><span class="sxs-lookup"><span data-stu-id="139ff-102">Signing in and using Lync 2013 on the virtual machine</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="139ff-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="139ff-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="139ff-104">После включения подключаемого модуля VDI при входе пользователя в Lync 2013 выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="139ff-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="139ff-105">Пользователь вводит свои учетные данные в клиент Lync 2013, работающий на виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="139ff-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="139ff-106">После того как Lync обнаружит доступность подключаемого модуля VDI, Lync предложит пользователю повторно ввести свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="139ff-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="139ff-107">Рекомендуется, чтобы пользователь установил флажок **Сохранить пароль** в этом диалоговом окне, так как в этом случае ему не придется вводить свои учетные данные при последующем входе в систему.</span><span class="sxs-lookup"><span data-stu-id="139ff-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="139ff-108">Lync начинает связывание с подключаемым модулем VDI.</span><span class="sxs-lookup"><span data-stu-id="139ff-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="139ff-109">До завершения связывания клиент отображает два значка в строке состояния Lync.</span><span class="sxs-lookup"><span data-stu-id="139ff-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="139ff-110">Значок в нижнем левом углу указывает на то, что доступные аудиоустройства отсутствуют, а мигающий значок в нижнем правом углу — на то, что выполняется процесс сопряжения VDI, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="139ff-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="139ff-111">![Значок VDI для Lync, иллюстрирующий успешные операции связывания](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Значок VDI для Lync, иллюстрирующий успешные операции связывания")</span><span class="sxs-lookup"><span data-stu-id="139ff-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="139ff-112">После успешного сопряжения подключаемого модуля VDI значки изменяются и теперь обозначают аудиоустройство, которое будет использоваться для выполнения вызовов, и успешное сопряжение VDI:</span><span class="sxs-lookup"><span data-stu-id="139ff-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="139ff-113">![Значок связывания VDI Lync с успешным выполнением](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Значок связывания VDI Lync с успешным выполнением")</span><span class="sxs-lookup"><span data-stu-id="139ff-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="139ff-114">После пар Lync с подключаемым модулем VDI пользователь может видеть сведения о присутствии устройств, совместимых с Lync, подключенных к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="139ff-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="139ff-115">Теперь пользователь может выполнять вызовы и отвечать на них в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="139ff-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

