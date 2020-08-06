---
title: Classe SqlServerAlias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583416"
---
# <a name="sqlserveralias-class"></a>Classe SqlServerAlias
  A classe [da classe SqlServerAlias](sqlserveralias-class.md) representa um alias de conexão de servidor.  
  
 Um alias de conexão de servidor é necessário quando as seguintes situações ocorrerem:  
  
-   O cliente está se conectando a uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um transporte de rede que não é o transporte de rede padrão.  
  
-   A instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para o qual o cliente é conectado escuta em um pipe nomeado alternativo.  
  
 **Observação:** A [classe SqlServerAlias](sqlserveralias-class.md) herda o `Put` método da classe Provider. Porém, ela não retorna nenhum resultado como indicado pelo método `Provider::Put`. Para obter mais informações, consulte a documentação do WMI.  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
