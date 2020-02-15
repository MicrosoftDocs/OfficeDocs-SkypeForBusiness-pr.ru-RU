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
ms.openlocfilehash: 912bf3c2c30474755fbefd7399f110ae898fc104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="bbc59-102">Настройка параметров рисунков по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbc59-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbc59-103">_**Последнее изменение темы:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="bbc59-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="bbc59-104">По умолчанию изображения пользователей автоматически отображаются.</span><span class="sxs-lookup"><span data-stu-id="bbc59-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="bbc59-105">Если пользователи хотят скрыть изображения, они могут выбрать параметр **Скрыть мое изображение** в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="bbc59-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="bbc59-106">Тем не менее, этот параметр игнорируется некоторыми другими приложениями Office.</span><span class="sxs-lookup"><span data-stu-id="bbc59-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="bbc59-107">Если возможность отображать изображения даже при отключенных пользователях, то вы можете изменить параметры отображения изображений Lync на глобальном уровне или для сайта или службы, чтобы изображения пользователей не отображались по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbc59-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="bbc59-108">Используйте приведенный ниже командлет командной консоли Lync Server, чтобы изображения пользователя не отображались, пока не будет явно выбран параметр **Показать изображение** в клиенте:</span><span class="sxs-lookup"><span data-stu-id="bbc59-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="bbc59-109">Для получения дополнительных сведений об этом командлете обратитесь к разделу [Set – CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbc59-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

