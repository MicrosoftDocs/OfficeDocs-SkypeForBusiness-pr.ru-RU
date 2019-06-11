---
title: 'Lync Server 2013: Настройка параметров рисунка по умолчанию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f41fa8fb590b2f5bc2e38db9a72545e13fb8d73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Настройка параметров рисунка по умолчанию в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-22_

По умолчанию рисунки пользователей отображаются автоматически. Если пользователи хотят скрыть свои рисунки, они смогут выбрать параметр **скрыть мою фотографию** в клиенте Lync. Тем не менее этот параметр игнорируется некоторыми другими приложениями Office.

Если возможность отображения рисунков даже при выключенном пользователе является проблемой, вы можете изменить параметры отображения рисунков Lync глобально или для сайта или службы таким образом, чтобы изображения пользователей не отображались по умолчанию. Используйте следующий командлет командной консоли Lync Server, чтобы изображения пользователя не отображались, пока не будет явно указан параметр " **Показывать мои рисунки** " в клиенте:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Дополнительные сведения об этом командлете можно найти в документации [Set-кспривациконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) в командной консоли Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

