---
title: FAQ for the Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 'Средство Stress and Performance в Skype для бизнеса 2015: часто задаваемы вопросы и ответы, полезное для поиска поддерживаемых конфигураций средств, устранения неполадок и уточнения действий, которые могут возникнуть при запуске средств Stress and Performance.'
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814969"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>FAQ for the Skype for Business Server 2015 Stress and Performance Tool
 
Средство Stress and Performance в Skype для бизнеса 2015: часто задаваемы вопросы и ответы, полезное для поиска поддерживаемых конфигураций средств, устранения неполадок и уточнения действий, которые могут возникнуть при запуске средств Stress and Performance.
  
 This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Можно ли запускать LyncPerfTool.exe в производственной?

Это **не рекомендуется.** Это средство повлияет на производительность, безопасность и работу конечных пользователей на производственном сервере.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>I'm logging my users on for the first time. Почему на серверах работает высокая нагрузка?

При первом входе пользователей в систему в фоновом режиме происходят дополнительные операции. В результате производительность на Microsoft SQL Server тыловом сервере может ухудшиться. Рекомендуется выполнить короткий тест, который занося в журнал для всех пользователей, а затем перезапустить клиенты, прежде чем начать измерять результаты с помощью средства. Skype для бизнеса Server не поддерживает более 12 сеансов одновременного пользователя в секунду, но следует помнить, что фактическое число, которое может обрабатываться серверами, зависит от конфигурации оборудования и может быть меньше поддерживаемого значения.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>У моих клиентов заканчивается память! Что делать?

Если на клиентах заканчивается память, следует уменьшить количество пользователей, во время входа в систему в пуле переднего сервера Skype для бизнеса Server. Вы также можете масштабировать пулы переднего уровня, если проблема сохраняема.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Можно ли запустить это средство на самом сервере Skype для бизнеса?

Это не следует делать. Этот сценарий не поддерживается, так как он может привести к ошибке из-за несоответствия двоичных данных, а также из-за того, что целью является измерение потребления ресурсов на сервере. Фактический запуск средства влияет на производительность сервера и аннулирует данные и показатели.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Можно ли запускать LyncPerfTool.exe на виртуальном сервере или в Microsoft Hyper-V Server 2008/2012?

Да, Вы можете.
  
## <a name="what-does-mpop-mean"></a>Что означает MPOP?

MPOP — это сокращенный способ слова "несколько точек присутствия". MPOP предназначен для имитации сценариев, в которых пользователи вошел в клиент Skype для бизнеса 2015 с нескольких компьютеров или устройств. Следует помнить, что в LyncPerfTool.exe каждой конечной точке используется профиль по умолчанию. Другими словами, профиль не делится между двумя точками присутствия.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Я начал LyncPerfTool.exe, но ничего не происходит. Почему?

Проверьте счетчик "Всего активных конечных точек" на серверах, чтобы узнать, подключаются ли пользователи. Если пользователи не подключаются, проверьте конфигурацию Skype для бизнеса Server 2015. Проблема обычно возникает из-за неправильного имени сервера, префикса пользователя или пароля. Обратите внимание, что внешние клиенты должны указывать значения прокси-сервера Access и TargetServer. Проверьте номер порта в файле конфигурации.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Как убедиться, что что-то измеряется?

Существуют счетчики производительности LyncPerfTool, которые указывают, подключаются ли пользователи и выполняют действия, но самый простой способ измерения действий — войти в одну из учетных записей с клиентом Skype для бизнеса 2015 и выполнить эти действия самостоятельно. Проверьте результаты, чтобы подтвердить, что были приняты измерения.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>У меня установлены средства планирования емкости Lync Server 2010 и(или) Lync Server 2013. Это нормально?

 У этих средств есть проблемы со совмедомостью! Чтобы получить допустимые данные из средства Stress and Performance Skype для бизнеса Server 2015, необходимо удалить все предыдущие версии этих средств.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Будут ли средства stress and Performance устанавливать топологию сервера информации о вызовах CAA?

Нет, средства не будут этого делать. Эти средства создают пользователей, контакты и списки рассылки только для имитации пользовательской нагрузки.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Каково максимальное число пользователей, поддерживаемых средствами?

В ходе тестирования мы создали до 80 000 пользователей и выполнили тесты для 30 000 пользователей, запускающих эти средства. Мы предлагаем не более 120 000 пользователей, хотя технические ограничения позволяют использовать более высокие значения. Помните, что эти значения зависят от сервера и оборудования в вашей среде.
  

