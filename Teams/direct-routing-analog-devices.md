---
title: Прямая маршрутизация – подключение аналоговых устройств
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Прочтите эту статью, чтобы научиться использовать аналоговые устройства с прямой маршрутизацией Microsoft Phone System.
ms.openlocfilehash: 0c6531a29e23e736a84db9bf8571abab2e13942a
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369194"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Как использовать аналоговые устройства с прямой маршрутизацией телефонной системы

В этой статье рассказывается, как использовать аналоговые устройства с прямой маршрутизацией телефонной системы. Чтобы соединить аналоговые устройства с прямой маршрутизацией, необходимо использовать аналоговый адаптер телефонной связи (ATA), и этот адаптер должен поддерживаться поставщиком SBC-контроллера границ для сертифицированного сеанса. 

Когда пользователь выполняет звонок с аналогового устройства, передача сигналов и мультимедиа через аналоговый адаптер телефонной связи (ATA) в SBC.  SBC отправляет Звонок на конечную точку Microsoft Teams или коммутируемую телефонную сеть общего пользования (PSTN), основанную на таблице внутренней маршрутизации.  Когда устройство совершает звонок, маршрут будет зависеть от политики маршрутизации, созданной для устройства.

На приведенной ниже схеме прямая маршрутизация настраивается таким образом, чтобы любые звонки на другие команды и из них между элементами + 1425 4XX XX XX и + 1425 5XX XX XX должны принимать красный маршрут (пунктирная линия), а 1425 любой другой номер за исключением диапазонов номеров + 1425 5XX XX XX — синий маршрут (сплошная линия). 

> [!div class="mx-imgBorder"]
> ![Диаграмма, на которой показана прямая настройка маршрутизации](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Пример: Настройка использования аналоговых устройств с прямой маршрутизацией

Чтобы настроить использование аналоговых устройств с прямой маршрутизацией, необходимо подключить аналоговый адаптер телефонной связи к SBC и настроить SBC для прямого перенаправления. 

В этом примере вы просматриваете следующие шаги:

1. Соединение SBC для прямой маршрутизации.
2. Создание использования КТСОП.
3. Создайте голосовой маршрут и свяжите его с использованием КТСОП.
4. Назначайте голосовой маршрут для использования PSTN.
5. Включите пользователя Online.
6. Назначение пользователю политики голосовых маршрутов.
7. Создайте голосовой маршрут для аналогового устройства.

Сведения о том, как подключить ATA к SBC и настроить SBC, можно найти в руководстве по настройке производителей SBC.

- [Документация по конфигурации AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Документация по настройке ленты](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Шаг 1.  Соединение SBC для прямой маршрутизации

Следующая команда конфигурирует соединение SBC следующим образом:

- Полное доменное имя sbc.contoso.com
- Передача сигнала на порт 5068
- Режим обхода мультимедиа
- Данные журнала вызовов, переадресованные в SBC-
- Заголовок P-Assert-Identity (PAI), пересылаемый вместе с звонком 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Действие 2: создание использования PSTN 

Следующая команда создает пустое использование КТСОП. Сетевые сети PSTN — это строковые значения, которые используются для авторизации звонков. Использование сети PSTN – это связь политики голосовой связи через Интернет с маршрутом. Этот пример добавляет строку "взаимодействие" в текущий список доступных использований PSTN. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Шаг 3. Создайте голосовой маршрут и свяжите его с использованием КТСОП.

Эта команда создает новый голосовой маршрут с удостоверением "аналогово-Interop" для диапазона чисел + 1425 XXX XX XX.  Маршрут голосовой связи применим к списку интернет-шлюзов sbc.contoso.com и связывает маршрут с использованием взаимодействия по сети PSTN. Голосовой маршрут включает регулярное выражение, которое определяет, какие номера телефонов будут маршрутизироваться по данному голосовому маршруту.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Действие 4: назначьте голосовой маршрут для использования КТСОП:

Эта команда создает новую политику голосовой маршрутизации для пользователя Online с удостоверением "AnalogInteropPolicy". Этой политике назначается единая сетевая использование PSTN: "Interop".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Шаг 5: включение пользователя Online

Эта команда изменяет учетную запись пользователя с помощью удостоверения exampleuser@contoso.com. В этом случае учетная запись будет изменена, чтобы включить корпоративную голосовую связь (Майкрософт) по протоколу VoIP с включенной голосовой почтой и назначить номер + 14255000000 для этого пользователя.  Эту команду следует запускать для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Шаг 6: назначение пользователю политики маршрутов голосовой связи

Эта команда назначает пользователю политику маршрутизации голосовой связи "на пользователя", AnalogInteropPolicy удостоверением exampleuser@contoso.com.  Эту команду следует запускать для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Шаг 7: Создание голосового маршрута для аналогового устройства

Эта команда создает онлайновый маршрут с удостоверением "аналогово-Interop" для диапазона номеров + 1425 4XX XX XX, применимый к списку интернет-шлюзов sbc.contoso.com и связывающий его с помощью сети Интернет-ресурсов PSTN.  Эту команду следует запускать для каждого аналогового устройства с соответствующим шаблоном номера телефона. Кроме того, можно использовать правильный шаблон номера для аналоговых устройств при настройке голосового голосовой связи в течение одного из предыдущих шагов.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Рекомендации

- За исключением случаев, когда иное не стоит Примечание, Аналоговое устройство — это любое устройство, которое может отправлять звонки на DTMF-цифры. Например, аналоговые телефоны, факсимильные аппараты и пейджеры служебных данных.

- Аналоговые телефоны, подключенные к ATA, не поддерживают поиск в Teams. Пользователи Teams должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить этому устройству.  
 

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
