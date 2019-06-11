---
title: 'Lync Server 2013: развертывание корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Развертывание корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

Lync Server 2013, корпоративный голос является частью инфраструктуры Lync Server 2013.

Для развертывания корпоративной голосовой связи необходимо:

<div id="sectionSection0" class="section">

1.  Ознакомьтесь с разделом [планирование для корпоративного голосовой связи в Lync Server 2013 в](lync-server-2013-planning-for-enterprise-voice.md) документации по планированию.

2.  Завершайте планы для функций и компонентов, которые развертываются вместе с этой рабочей нагрузкой.

3.  Запустите средство планирования, чтобы спроектировать топологию, отражающую ваши решения по развертыванию.

4.  Откройте структуру топологии в построителе топологии, как описано в разделе [Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) в документации по развертыванию.
    
    <div>
    

    > [!NOTE]  
    > Установка Topology Builder входит в процесс развертывания внутреннего пула. Подробности можно найти в разделе <A href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</A> в документации по развертыванию.

    
    </div>

Кроме того, вы должны иметь уже развернутые Lync Server, Enterprise Edition на центральных сайтах и сайтах филиалов, которые соответствуют топологии ссылок, которую вы выбираете для развертывания. Вы не можете внедрять корпоративные голосовые компоненты, пока не будет определен, опубликован и не установлен ни один из внутренних файлов, а для определения и публикации внутреннего пула необходимо использовать Topology Builder.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Для просмотра эталонных топологий с примерами того, где разрешается развертывание ролей корпоративного голосового сервера (и их связь друг с другом и другими ролями сервера Lync Server 2013), ознакомьтесь с [эталонными топологиями в Lync server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.

Для просмотра топологии ссылок, в которой показано, а также объясняется пример развертывания элемента управления допуском звонков, включая регионы сети, сетевые сайты и подсети, смотрите [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в Документация по планированию.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Чтобы развернуть корпоративную голосовую почту на центральном сайте, продолжите чтение тем в этом разделе. Чтобы развернуть корпоративную голосовую почту на сайте филиала, перейдите к разделу <A href="lync-server-2013-deploying-branch-sites.md">Развертывание сайтов филиалов в Lync Server 2013</A> в документации по развертыванию.



</div>

В этом разделе описываются варианты развертывания с размещением сервера-посредника на каждом сервере переднего плана или сервере Standard Edition (рекомендуется), а также варианты развертывания отдельного пула cерверов-посредников.

Вы можете пропустить следующее содержимое, если вы используете Topology Builder, чтобы определить и опубликовать топологию, которая будет высвоена серверу-посреднику на каждом сервере переднего плана или стандартном сервере выпуска Standard Edition, так как мастер развертывания уже автоматически установил файлы для Сервер для устранения проблем при установке файлов для пула серверов переднего плана или стандартного выпуска сервера:

  - [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md)

Если вы использовали Topology Builder для определения и публикации сервера-посредника в отдельном пуле, вы можете использовать следующее содержимое:

  - Убедитесь, что ваша топология соответствует требованиям к программному обеспечению и среде, как описано в разделе [требования к корпоративной голосовой связи для Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - <span></span>  
    [Необходимые условия для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Настройка абонентских групп в Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Тестирование голосовой маршрутизации в Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Развертывание улучшенных функций голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [О сетевых областях, сайтах и подсетях в Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Создание или изменение сетевого региона в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Связь подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Настройка управления допуском звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Настройка службы Enhanced 9-1-1 в Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Настройка обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Включение пользователей корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание сайтов филиалов в Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Настройка конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Настройка парковки вызовов в Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Настройка объявлений для неназначенных номеров в Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

