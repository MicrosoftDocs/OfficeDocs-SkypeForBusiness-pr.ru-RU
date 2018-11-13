---
title: Запись собрания облачных групп
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e78abdbe7d0cc2680917f2aae7920883837a2ac9
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296390"
---
# <a name="teams-cloud-meeting-recording"></a>Запись собрания облачных групп

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

В Майкрософт для групп пользователи смогут вести запись их группами собрания и звонки из группы для захвата звука, видео- и экрана сеанс совместного доступа. Имеется также возможность записи иметь автоматическая подписка, чтобы пользователи могут воспроизведения собрания записей закрытых заголовков и искать важные элементы в записи. Записи происходит в облаке и сохраняется в [Microsoft потока](https://docs.microsoft.com/stream/), поэтому пользователи могут безопасное совместное использование его в организации.

Связанные: [собрания групп записи документации для конечных пользователей](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Необходимые условия для групп в облаке запись собрания

Для пользователей группам собраний для записи необходимо включить поток Microsoft для клиента. Кроме того Организатор собрания и человека, который инициирует записи требуются следующие необходимые компоненты:

- Пользователь имеет лицензии Office 365 корпоративный E1, E3 или E5
- Пользователю необходимо иметь лицензию для потока Microsoft
- Пользователь имеет Microsoft поток передачи видео разрешения
- Если пользователь изъявил рекомендации по организации, настройте, администратор
- Пользователь имеет достаточно места в потоке Microsoft для записи будет сохранен
- Пользователь имеет TeamsMeetingPolicy AllowCloudRecording не установлено значение true
- Пользователь имеет TeamsMeetingPolicy AllowTranscription установлено значение "true", поэтому пользователь может выбрать, следует ли автоматически переписать записи
- Пользователь не анонимного, гостя или федеративных пользователей на собрании

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Настройка групп запись собрания облаке для пользователей в вашей организации

В этом разделе объясняется, как можно настроить и спланировать записи собраний группы.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Предоставление пользователям в организации Microsoft потока

Поток Microsoft доступна как часть подходящими подписки на Office 365 или как автономную службу.  В разделе [Общие сведения о лицензировании поток](https://docs.microsoft.com/stream/license-overview) для получения дополнительных сведений.  Обратите внимание, что поток Майкрософт не включаются в Business Essentials или бизнеса расширенный планов.

Дополнительные сведения о как обеспечить [Назначение лицензий для пользователей в Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , чтобы пользователи могут получить доступ к потоку Microsoft. Убедитесь, что поток Майкрософт не блокируются для пользователей, как определено в [этой статье](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Убедитесь, что пользователи имеют отправляют разрешения видео в Microsoft потока

По умолчанию все сотрудники организации можно создавать содержимое в потоке, после потока включено, лицензия назначена для пользователя. Администратор Microsoft потока можно [ограничить сотрудников для создания контента](https://docs.microsoft.com/stream/restrict-uploaders) в потоке. Пользователям, входящим в этот список ограниченных не будет иметь возможность записи собрания.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Уведомлять сотрудников согласие на рекомендации по компании в потоке Microsoft

Если администратор Microsoft потока [настроить политику рекомендация компании](https://docs.microsoft.com/stream/company-policy-and-consent) и требует, чтобы сотрудники на прием данной политики перед сохранением контента, пользователям необходимо сделать до записи в группах Microsoft. Прежде чем единовременного средства для записи в организации убедитесь, что пользователи согласие в политике.

### <a name="enabledisable-cloud-recording-for-users"></a>Включение и отключение записи для пользователей облака

Используйте параметр AllowCloudRecording TeamsMeetingPolicy в команды PowerShell для управления ли собрания пользователя могут записать или нет. Дополнительные сведения об управлении TeamsMeetingPolicy с Office 365 PowerShell [здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Обратите внимание, что организатор собрания и инициатор записи необходимо иметь разрешения записи записывать собрание. Если для пользователей, которым назначен пользовательскую политику, пользователи получают глобальной политики, которая имеет AllowTranscription отключен по умолчанию.

Пользователь может вернуться к глобальной политики используйте следующий командлет для удаления назначения политики для пользователя:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Чтобы изменить значение AllowCloudRecording в глобальной политики, используйте следующий командлет:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Сценарий                                                                 |                                                                                                                                                                         Шаги                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Я хочу все пользователи в моей компании могут вести запись свои собрания                                    |                                                                     <ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowCloudRecording = True<li>Все пользователи имеют глобальные или CsTeamsMeetingPolicy одну из политик CsTeamsMeetingPolicy с AllowCloudRecording = True </ol>                                                                     |
| Требуется большая часть Мои пользователи должны иметь возможность записать свои собрания, но отключить пользователей, которым не допускается для записи |        <ol><li>Подтверждение GlobalCsTeamsMeetingPolicy имеет AllowCloudRecording = True<li>Большинство пользователей имеют глобального CsTeamsMeetingPolicy или один политик CsTeamsMeetingPolicy с AllowCloudRecording = True<li>Все пользователи имеют одну из политик CsTeamsMeetingPolicy с AllowCloudRecording = False</ol>         |
|                                                   Требуется запись быть отключено 100%                                                   |                                                                <ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowCloudRecording = False<li>Все пользователи были присвоены глобального CsTeamsMeetingPolicy или одну из политик CsTeamsMeetingPolicy с AllowCloudRecording = False                                                                 |
|      Требуется записи отключены для большинства пользователей, но выборочно включить конкретных пользователей, которым разрешено для записи       | <ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowCloudRecording = False<li>Большинство пользователей были присвоены глобального CsTeamsMeetingPolicy или один политик CsTeamsMeetingPolicy с AllowCloudRecording = False<li>Все пользователи имеют одну из политик CsTeamsMeetingPolicy с AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="enabledisable-recording-transcription-for-users"></a>Включение и отключение записи транскрибирования для пользователей

Когда пользователи запишите свои собрания групп, они убедитесь, ли сообщения автоматически будет создан после собрания. При отключении транскрибирования возможность для организатора собрания и инициатор записи администраторов инициатор записи не будет возможность переписать записи собрания.

Используйте параметр AllowTranscription в TeamsMeetingPolicy в команды PowerShell для управления ли записи инициатор получает возможность переписать запись собрания. Дополнительные сведения об управлении TeamsMeetingPolicy с Office 365 PowerShell [здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Если для пользователей, которым назначен пользовательскую политику, получают глобальной политики, которая отключена в включена по умолчанию.

Пользователь может вернуться к глобальной политики используйте следующий командлет для удаления назначения политики для пользователя:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Чтобы изменить значение AllowCloudRecording в глобальной политики, используйте следующий командлет:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Сценарий|Шаги |
|---|---|
|Я хочу все пользователи в моей компании должны иметь возможность переписать при начале записи собрания |<ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowTranscription = True <li>Все пользователи имеют глобального csTeamsMeetingPolicy или одного из политик CsTeamsMeetingPolicy с AllowTranscription = True. </ol>|
|Требуется большая часть Мои пользователи должны иметь возможность переписать записи собраний, но отключить пользователей, которым не разрешается переписать |<ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowTranscription = True <li>Большинство пользователей имеют глобального CsTeamsMeetingPolicy или один политик CsTeamsMeetingPolicy с AllowTranscription = True <li>Все пользователи имеют одну из политик CsTeamsMeetingPolicy с AllowTranscription = False </ol>|
|Требуется подписка на запись быть отключено 100% |<ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowTranscription = False <li>Все пользователи были присвоены глобального CsTeamsMeetingPolicy или одну из политик CsTeamsMeetingPolicy с AllowTranscription = False </ol>|
|Требуется транскрибирования отключены для большинства пользователей, но выборочно включить пользователей, которым разрешено переписать |<ol><li>Подтверждение глобального CsTeamsMeetingPolicy имеет AllowCloudRecording = False <li>Большинство пользователей были присвоены глобального CsTeamsMeetingPolicy или один политик CsTeamsMeetingPolicy с AllowCloudRecording = False <li>Все пользователи имеют одну из политик CsTeamsMeetingPolicy с AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Планирование хранилища

Размер 1 час записи составляет 400 МБ. Убедитесь, что понять мощности, необходимые для записанные файлы и иметь достаточно дискового пространства, доступного в потоке Microsoft.  Чтение [в этой статье](https://docs.microsoft.com/stream/license-overview) описаны базового хранилища, включенные в подписку и как приобрести дополнительное хранилище.

## <a name="manage-meeting-recordings"></a>Управление записями собрания
Записи собраний, считаются клиента владельцем содержимого. Если владелец записи из компании, администратор можно открыть URL-адрес видеоролика записи в потоке Microsoft в режиме администратором. Администратор может удалить записи, обновлять метаданные записи и изменять разрешения для записи видео. Дополнительные сведения о [возможностях администрирования в поток](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Соответствие требованиям и обнаружение электронных данных для записи на собрания
Записи собраний, хранятся в Microsoft поток, который является Office 365 уровня-C спецификации. Чтобы обеспечить поддержку запросов на электронное обнаружение для соответствия требованиям администраторов, которые хотят собрания или звонок записей для потоков Microsoft, завершенных сообщения запись доступна в функции поиска контента соответствия требованиям для групп Майкрософт. Соответствие "Администраторы" можно искать ключевое слово «запись» в поле Тема элемента в предварительной версии содержимого поиска соответствия требованиям и обнаружение собрания и вызова записей в организации. Предварительным условием является их для просмотра всех записей — это, что их необходимо настроить в Microsoft потока с помощью административного доступа. Дополнительные сведения о [назначении разрешения администратора в поток](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, при внесении изменений параметров для нескольких пользователей за один раз. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Настройка компьютера для Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

