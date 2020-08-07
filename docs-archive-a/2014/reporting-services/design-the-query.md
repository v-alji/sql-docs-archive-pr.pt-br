---
title: Criar a consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682163"
---
# <a name="design-the-query"></a>Projetar a consulta
  Use esta página do Assistente de Relatório para criar uma consulta, digitando a consulta manualmente, usando o Construtor de Consultas para criar uma consulta interativamente ou importando uma consulta de outro relatório.  
  
 O tipo de fonte de dados que você escolheu na página Selecionar a Fonte de Dados, uma página anterior do Assistente de Relatório, determina a consulta que você pode digitar nessa página. Por exemplo, se o tipo de fonte de dados for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , você poderá inserir [!INCLUDE[tsql](../includes/tsql-md.md)] instruções ou nomes de procedimento armazenado. Se o tipo de fonte de dados for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , o painel de consulta será desabilitado e você não poderá inserir uma consulta diretamente. Você pode especificar a consulta usando o Construtor de Consultas.  
  
## <a name="options"></a>Opções  
 **Cadeia de consulta**  
 Digite uma consulta que recupere os dados que você deseja usar em seu relatório.  
  
 **Construtor de Consultas**  
 Clique em **Construtor de Consultas** para abrir um designer de consulta para a fonte de dados ou importar uma consulta de outro relatório.  
  
 Para obter mais informações sobre designers de consulta, consulte [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Exemplo  
 Para o tipo de fonte de dados **Microsoft SQL Server**, a consulta a seguir recupera uma lista de últimos nomes da tabela de banco de dado [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Para o tipo de fonte de dados **Microsoft SQL Server**, a consulta a seguir executa o [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procedimento armazenado `uspGetEmployeeManagers` para o funcionário com identificação número 1:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Ajuda do assistente de relatório](../../2014/reporting-services/report-wizard-help.md)   
 [Conjuntos de itens de relatório inseridos e conjuntos de &#40;compartilhados Construtor de Relatórios e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
