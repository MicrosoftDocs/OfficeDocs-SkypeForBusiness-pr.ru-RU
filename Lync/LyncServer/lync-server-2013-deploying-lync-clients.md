---
title: 'Lync Server 2013: развертывание клиентов Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad8735834ab004753444849c529cb4ceec18c16
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Развертывание клиентов Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

В Lync 2013 используется другой подход к развертыванию клиента. В отъезде из предыдущих выпусков Lync 2013 больше не имеет собственного установщика. Вместо этого Lync включен в программу установки Office 2013. Чтобы развернуть Lync 2013 для пользователей, вы можете использовать методы установки и средства настройки Office 2013.

  - **Office 2013 установщик Windows** — это пакет установки на основе установщика Windows, состоящий из нескольких MSI-файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. В подразделах этого раздела описывается, как использовать и настраивать установщик Office 2013 для развертывания Lync 2013.

  - **Office 2013 нажми и работай** — это программа установки, которая создает поток файлов установки Office для пользователя из центра администрирования Microsoft 365. Администраторы могут настраивать установку с помощью средства развертывания Office для технологии "Нажми и работай". Так как Office 2013 нажми и работай в основном используется в среде Microsoft Office 365, этот метод установки не подробно описан в этом разделе. Подробные сведения об использовании и настройке установки "нажми и работай" доступны в документации по набору ресурсов Office 2013. Кроме того, администраторы могут загрузить файлы и языковые файлы Office 2013 нажми и работай в локальное расположение, что удобно, если необходимо минимизировать потребность в сети или запретить пользователям устанавливать программное обеспечение из Интернета из-за требований к безопасности в корпоративной среде.

В подразделах этого раздела основное внимание уделяется развертыванию клиентов с помощью установщика Office 2013 на основе MSI. Основной ссылкой должна быть документация по набору ресурсов Office 2013, в которой подробно описывается подготовка инфраструктуры, Настройка установки и развертывание Office 2013. Тем не менее, следует использовать документацию по Office в сочетании с подразделами этого раздела, в которых рассматриваются вопросы развертывания, характерные для Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Надстройка "собрание по сети" для Lync 2013, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, устанавливается автоматически вместе с Lync 2013.</P>
> <LI>
> <P>Программа установки Office 2013 не удаляет предыдущие версии Lync или Office Communicator. Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка установки клиента в Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Настройка поведения Lync и пользовательского интерфейса в Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Настройка надстройки "собрание по сети" в Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Настройка страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Настройка поддерживаемых версий клиентов в Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Настройка режима конфиденциальности расширенных сведений о присутствии в Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

