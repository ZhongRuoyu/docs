---
ms.openlocfilehash: f95dd69778640ad4be04e0bfdab340d351845c38
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2022
ms.locfileid: "147066013"
---
Проверяет, что данные старше 400 дней архивируются. В процессе архивации {% data variables.product.prodname_dotcom %} создает состояние фиксации свертки, которое представляет состояние всех проверок для этой фиксации. Как следствие, поле слияния в любом запросе на вытягивание с обязательными проверками архивации будет находиться в заблокированном состоянии, и перед слиянием такого запроса на вытягивание придется повторно запустить эти проверки.