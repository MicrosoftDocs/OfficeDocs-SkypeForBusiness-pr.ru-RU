---
title: загрузка топологии из существующего развертывания;
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903b115eaa820245135e0bc2c3650ba596c5d925
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502906"
---
# <a name="download-topology-from-existing-deployment"></a>загрузка топологии из существующего развертывания;

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

При создании пула Lync Server 2013 вы будете использовать центральное хранилище управления, связанное с Lync Server 2010. При запуске построителя топологий при первом использовании и в последующих сеансах редактирования, отображается запрос на ввод расположения, из которого построитель топологий должен загрузить текущий документ конфигурации. Так как вы уже определили топологию Lync Server 2010 и установили центральное хранилище управления, необходимо выбрать загрузку топологии из существующего развертывания. Построитель топологии прочитает базу данных и извлечет текущее определение.

**Загрузка топологии из существующего развертывания**

1.  Откройте **мастер развертывания Lync Server**.

2.  На странице **Lync Server 2013 — мастер развертывания** нажмите кнопку **Установить средства администрирования**.

3.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013** и **Построитель топологий Lync Server**.

4.  Выберите пункт **Download Topology from existing deployment** (Загрузить топологию из существующего развертывания).
    
    ![Параметры построителя топологии мастера развертывания](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Параметры построителя топологии мастера развертывания")

5.  Выберите имя файла и сохраните топологию с типом файла по умолчанию (TBXML).

6.  Разверните узел Lync Server, как показано, чтобы отобразить различные роли сервера в развертывании.
    
    ![Общие свойства роли сервера построителя топологии](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Общие свойства роли сервера построителя топологии")

</div>

<span> </span>

</div>

</div>

</div>

