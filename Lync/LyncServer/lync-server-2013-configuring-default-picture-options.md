---
title: 'Lync Server 2013: Настройка параметров рисунка по умолчанию'
description: 'Lync Server 2013: Настройка параметров рисунка по умолчанию.'
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
ms.openlocfilehash: 6261aca82b4c71eb8e0573e8d2adbfc008e743fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558005"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Настройка параметров рисунков по умолчанию в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-22_

По умолчанию изображения пользователей автоматически отображаются. Если пользователи хотят скрыть изображения, они могут выбрать параметр **Скрыть мое изображение** в клиенте Lync. Тем не менее, этот параметр игнорируется некоторыми другими приложениями Office.

Если возможность отображать изображения даже при отключенных пользователях, то вы можете изменить параметры отображения изображений Lync на глобальном уровне или для сайта или службы, чтобы изображения пользователей не отображались по умолчанию. Используйте приведенный ниже командлет командной консоли Lync Server, чтобы изображения пользователя не отображались, пока не будет явно выбран параметр **Показать изображение** в клиенте:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Для получения дополнительных сведений об этом командлете обратитесь к разделу [Set – CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) в документации по консоли управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

