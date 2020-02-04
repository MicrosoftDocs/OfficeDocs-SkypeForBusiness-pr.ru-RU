---
title: 'Lync Server 2013: Настройка параметров рисунка по умолчанию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e551d069da9a3afb7a884c28096dd97ab3702539
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="779e6-102">Настройка параметров рисунка по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="779e6-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779e6-103">_**Тема последнего изменения:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="779e6-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="779e6-104">По умолчанию рисунки пользователей отображаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="779e6-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="779e6-105">Если пользователи хотят скрыть свои рисунки, они смогут выбрать параметр **скрыть мою фотографию** в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="779e6-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="779e6-106">Тем не менее этот параметр игнорируется некоторыми другими приложениями Office.</span><span class="sxs-lookup"><span data-stu-id="779e6-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="779e6-107">Если возможность отображения рисунков даже при выключенном пользователе является проблемой, вы можете изменить параметры отображения рисунков Lync глобально или для сайта или службы таким образом, чтобы изображения пользователей не отображались по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="779e6-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="779e6-108">Используйте следующий командлет командной консоли Lync Server, чтобы изображения пользователя не отображались, пока не будет явно указан параметр " **Показывать мои рисунки** " в клиенте:</span><span class="sxs-lookup"><span data-stu-id="779e6-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="779e6-109">Дополнительные сведения об этом командлете можно найти в документации [Set-кспривациконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="779e6-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

