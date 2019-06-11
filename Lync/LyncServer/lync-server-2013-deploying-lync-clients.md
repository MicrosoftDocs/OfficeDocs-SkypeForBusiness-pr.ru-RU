---
title: 'Lync Server 2013: развертывание клиентов Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Развертывание клиентов Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

В Lync 2013 представлен другой подход к развертыванию клиента. В отъезде из предыдущих выпусков Lync 2013 больше не имеет собственного установщика. Вместо этого Lync входит в состав программы установки Office 2013. Чтобы развернуть Lync 2013 для пользователей, вы можете использовать способы установки Office 2013 и средства настройки.

  - **Установщик windows 2013 Office** — это установочный пакет установщика Windows, состоящий из нескольких MSI-файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. В этой статье описано, как использовать и настраивать установщик Windows 2013 для развертывания Lync 2013.

  - **Office 2013 нажми** и работай — это программа установки, с помощью которой можно перепотокировать файлы установки Office на портале Microsoft Office 365. Администраторы могут настраивать установку с помощью средства развертывания Office для технологии "Нажми и работай". Поскольку в Office 2013 технология "нажми и работай" используется преимущественно в среде Microsoft Office 365, этот способ установки не подробно описан в этом разделе. Подробные сведения об использовании и настройке установки "нажми и работай" можно найти в документации по набору ресурсов Office 2013. Кроме того, администраторы могут загрузить файлы исходного кода и языковых файлов Office 2013 в локальное расположение, что бывает полезно, если вы хотите минимизировать требования к сети или запретить пользователям устанавливать программное обеспечение из Интернета из-за корпоративные требования к безопасности.

В этом разделе содержатся сведения о развертывании клиентов с помощью установщика Office 2013 на базе MSI. Основной ссылкой является документация по набору ресурсов Office 2013, в которой подробно описана процедура подготовки инфраструктуры, Настройка настройки и развертывание Office 2013. Тем не менее, вы должны использовать документацию Office в сочетании с разделами в этом разделе, которые указывают на вопросы по развертыванию, специфичные для Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Надстройка "собрание по сети" для Lync 2013, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы в Outlook, устанавливается автоматически с помощью Lync 2013.</P>
> <LI>
> <P>Программа установки Office 2013 не удаляет предыдущие версии Lync и Office Communicator. Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка установки клиента в Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Настройка поведения Lync и пользовательского интерфейса в Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Настройка надстройки "собрание по сети" в Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Конфигурация страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Настройка поддерживаемых клиентских версий в Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Настройка режима конфиденциальности для расширенного присутствия в Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

