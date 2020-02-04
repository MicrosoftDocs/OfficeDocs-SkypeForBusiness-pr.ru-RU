---
title: загрузка топологии из существующего развертывания;
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>загрузка топологии из существующего развертывания;

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-29_

При создании пула Lync Server 2013 вы будете использовать хранилище Central Management, связанное с Lync Server 2010. Когда вы запускаете построитель топологии при первом использовании и последующих сеансах редактирования, вам будет предложено указать расположение, в которое построитель топологии должен загрузить текущий документ конфигурации. Так как вы уже определили топологию Lync Server 2010 и установили хранилище Central Management, необходимо выбрать загрузку топологии из существующего развертывания. Построитель топологии будет считывать базу данных и получать текущее определение.

**Загрузка топологии из существующего развертывания**

1.  Запустите **Мастер развертывания Lync Server**.

2.  На странице **мастера развертывания Lync Server 2013 —** **Установка средств администрирования**.

3.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013** и нажмите кнопку **Построитель топологии Lync Server**.

4.  Выберите пункт **топология скачивания из существующего развертывания**.
    
    ![Параметры Topology Builder мастера развертывания](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Параметры Topology Builder мастера развертывания")

5.  Выберите имя файла и сохраните топологию с типом файла Default. тбксмл.

6.  Разверните узел Lync Server, как показано на рисунке, чтобы показать различные роли сервера в развертывании.
    
    ![Общие свойства роли сервера построителя топологии](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Общие свойства роли сервера построителя топологии")

</div>

<span> </span>

</div>

</div>

</div>

