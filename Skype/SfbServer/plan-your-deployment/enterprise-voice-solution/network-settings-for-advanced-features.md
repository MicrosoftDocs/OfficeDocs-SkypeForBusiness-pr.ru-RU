---
title: Параметры сети для расширенных Корпоративная голосовая связь в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Узнайте о областях сети, сетевых сайтах и IP-подсетях. Все они должны быть настроены для развертывания плана обхода сервера-посредника в Skype для бизнеса, плана контроля допуска звонков в Skype для бизнеса Server или планирования экстренных служб в Skype для бизнеса Server в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 3f7b11d2265c9b5f93633b03311d622ad9862abd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813629"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Параметры сети для расширенных Корпоративная голосовая связь в Skype для бизнеса Server

Узнайте о областях сети, сетевых сайтах и IP-подсетях. All these must be configured to deploy [Plan for media bypass in Skype for Business](media-bypass.md), Plan for call admission control in Skype for Business [Server](call-admission-control.md), or Plan [for emergency services in Skype for Business Server](emergency-services.md) in Skype for Business Server Корпоративная голосовая связь.

Skype для бизнеса Server имеет три расширенных Корпоративная голосовая связь: планирование контроля допуска звонков в Skype для бизнеса [Server,](call-admission-control.md)планирование экстренных служб [в Skype](emergency-services.md)для бизнеса Server и планирование обхода сервера-посредника в Skype [для бизнеса.](media-bypass.md) Эти функции имеют определенные требования к конфигурации для областей сети, сетевых сайтов и связи каждой подсети в топологии Skype для бизнеса Server с сетевым сайтом.

В этом разделе представлен обзор требований к конфигурации, общих для всех трех этих расширенных Корпоративная голосовая связь компонентов.

## <a name="network-regions"></a>Области сети

Область сети — это сетевой концентратор или сетевая магистраль, которая используется только в конфигурации контроля допуска звонков (CAC), служб экстренной помощи и обхода сервера-посредника.

> [!NOTE]
> Сетевые регионы не такие же, как регионы для телефонной связи Skype для бизнеса Server, которые необходимы для связи номеров доступа к этой услуге с одной или более телефонными номерами Skype для бизнеса Server. Подробные сведения о регионах, в которые можно использовать для телефонной видеоконференции, см. в этой [теме.](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx)

Cac requires that every network region have an associated Skype for Business Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established). Центральные сайты Skype для бизнеса Server представляют не географические расположения, а логические группы серверов, настроенные как пул или набор пулов.

To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Skype for Business Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Skype for Business Server Management Shell cmdlets. Инструкции см. в документации по развертыванию областей [сети,](../../deploy/deploy-enterprise-voice/deploy-network.md) сайтов и подсетей в Skype для бизнеса или в документации по skype для бизнеса Server Management Shell.

Все три расширенных функции Корпоративная голосовая связь общими определениями областей сети. Если области сети уже были созданы для одной функции, то для остальных функций не требуется создавать новые области сети. Однако может потребоваться изменить существующее определение области сети, чтобы применить параметры для определенной функции. Например, если созданы области сети для служб экстренной помощи (которым не требуется связанный центральный сайт), а затем разворачивается контроль допуска звонков, то необходимо изменить каждое определение областей сети, чтобы указать центральный сайт.

To associate a Skype for Business Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Skype for Business Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** cmdlets. Инструкции см. в документации по развертыванию областей [сети,](../../deploy/deploy-enterprise-voice/deploy-network.md) сайтов и подсетей в Skype для бизнеса или в документации по skype для бизнеса Server Management Shell.

## <a name="network-sites"></a>Узлы сети

Узел сети представляет географическое расположение, такое как филиал, региональное отделение или главный офис. Каждый узел сети должен быть связан с конкретной областью сети.

> [!NOTE]
> Сетевые сайты используются только расширенными функциями Корпоративная голосовая связь сети. Они не такие, как сайты филиалов, настроенные в топологии Skype для бизнеса Server.

To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Skype for Business Server Control Panel, or run the Skype for Business Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets. For details, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) in the Deployment documentation, or refer to the Skype for Business Server Management Shell documentation.

## <a name="identify-ip-subnets"></a>Идентификация IP-подсетей

Для каждого узла сети потребуется совместно с администратором сети определить, какая IP-подсеть назначена этому узлу сети. Если ваш администратор сети уже организовал IP-подсети в области сети и в узлы сети, то ваша работа значительно облегчается.

В нашем примере узлу New York в области North America назначены следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Когда Боб, который обычно работает в Детройте, приезжает в офис в Нью-Йорке для прохождения обучения, он включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех диапазонов, выделенных для Нью-Йорка, например 172.29.80.103.

> [!CAUTION]
> IP-подсети, заданные во время конфигурации сети на сервере, должны соответствовать формату, предоставленному клиентскими компьютерами, чтобы они использовались соответствующим образом для обхода сервера-посредника. Клиент Skype для бизнеса принимает свой локальный IP-адрес и маскирует IP-адрес с помощью связанной маски подсети. При определении идентификатора обхода, связанного с каждым клиентом, регистратор будет сравнивать список IP-подсетей, связанных с каждым узлом сети, с подсетью, предоставленной клиентом, и искать точное совпадение. По этой причине важно, чтобы подсети, указанные при конфигурации сети на сервере, были не виртуальными, а реальными подсетями. (Если развернуть контроль допуска вызовов, но не обход мультимедиа, контроль допуска вызовов будет работать правильно даже при настройке виртуальных подсетей.) Например, если клиент Skype для бизнеса вошел на компьютер с IP-адресом 172.29.81.57 с маской IP-подсети 255.255.255.0, он запросит ид обхода, связанный с подсети 172.29.81.0. Если подсеть определена как 172.29.0.0/16, то хотя клиент принадлежит этой виртуальной подсети, регистратор не будет считать это соответствием, поскольку точно ищет подсеть 172.29.81.0. Поэтому важно, чтобы администратор вводит подсети в точности в том виде, в котором они предоставляются клиентами Skype для бизнеса (которые предоставляются подсетями во время настройки сети либо статически, либо по протоколу DHCP).)

## <a name="associating-subnets-with-network-sites"></a>Сопоставление подсетей с узлами сети

Каждая подсеть в корпоративной сети должна быть связана с узлом сети (т.е. каждая подсеть должна быть связана с географическим расположением). Эта связь подсетей позволяет расширенным функциям Корпоративная голосовая связь находить конечные точки географически. Например, обнаружение конечных точек позволяет контролю допуска звонков регулировать поток аудио- и видеоданных в режиме реального времени, приходящий в этот узел сети и выходящий из него.

Чтобы связать подсети с сетевыми сайтами, можно использовать раздел "Конфигурация сети" панели управления Skype для бизнеса Server или с помощью оболочки управления Skype для бизнеса Server.  Инструкции см. [](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) в документации по развертыванию "Связывание подсети с сетевым сайтом" или в документации по skype для бизнеса Server Management Shell.

## <a name="see-also"></a>См. также

[Планирование контроля допуска звонков в Skype для бизнеса Server](call-admission-control.md)

[Планирование экстренных служб в Skype для бизнеса Server](emergency-services.md)

[Планирование обхода мультимедиа в Skype для бизнеса](media-bypass.md)

