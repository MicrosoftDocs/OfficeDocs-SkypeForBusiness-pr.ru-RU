---
title: Создание и Настройка политик пользователей для архивации в Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8c3c83f06f7bc01d81acc18cb0c9cedb4b0ef7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Создание и Настройка политик пользователей для архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Чтобы включить или отключить архивацию для отдельных пользователей, размещенных на Lync Server, необходимо сначала создать политику пользователя, а затем применить эту политику к одному или нескольким пользователям или группам пользователей. Сведения о применении политик пользователей к определенным пользователям и группам пользователей приведены в статье [применение политики архивации Lync Server к пользователю в Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.

Сведения о том, как работают политики архивации, [2013 в](lync-server-2013-how-archiving-works.md) том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье по планированию, в документации по развертыванию или в документации по работе.

<div>


> [!NOTE]
> Если для развертывания включена интеграция с Microsoft Exchange, политики хранения на месте Exchange контролируют, включено ли архивирование для пользователей, размещенных в Exchange 2013 и почтовые ящики, которые помещаются на удержание на месте. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации. Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Настройка политики архивации для пользователей, размещенных на сервере Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server 2013, можно найти в статье [Open the Lync server 2013 Tools администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Политика архивации**.

4.  Щелкните элемент **New** (Создать) и **User policy** (Политика пользователей).

5.  В окне **New Archiving Policy** (Новая политика архивации) выполните следующие действия:
    
      - В поле **Name** (Имя) укажите имя политики пользователей.
    
      - В поле **Description** (Описание) укажите сведения о том, что из себя представляет данная политика пользователей (например, политика пользователей для юридического отдела).
    
      - Чтобы контролировать архивацию внутренних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).
    
      - Чтобы контролировать архивацию внешних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).

6.  Щелкните элемент **Commit** (Исполнить).

Политика пользователей применяется только к тем пользователям, которым вы ее назначили. Сведения о применении политики пользователей к определенным пользователям приведены в статье [применение политики архивации Lync Server к пользователю в Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

