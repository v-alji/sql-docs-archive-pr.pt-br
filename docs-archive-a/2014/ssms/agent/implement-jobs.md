---
title: Implementar Trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent]
- SQL Server Agent jobs
- SQL Server Agent jobs, about jobs
- jobs [SQL Server Agent], about jobs
ms.assetid: 69e06724-25c7-4fb3-8a5b-3d4596f21756
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1925b3113db8d7c57ac4344958c0247763cfd1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569009"
---
# <a name="implement-jobs"></a>Implementar trabalhos
  É possível usar trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para automatizar tarefas administrativas de rotina e executá-las recorrentemente, tornando a administração mais eficaz.  
  
 Um trabalho é uma série especificada de operações executadas sequencialmente pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent. Um trabalho pode realizar uma ampla gama de atividades, tais como a execução de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] , aplicativos de linha de comando, scripts Microsoft ActiveX, pacotes do Integration Services, comandos e consultas do Analysis Services ou tarefas de replicação. Os trabalhos podem executar tarefas repetitivas ou agendáveis, bem como notificar usuários automaticamente sobre o status do trabalho por meio de alertas, desse modo simplificando bastante a administração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 É possível executar um trabalho manualmente ou configurá-lo para executar de acordo com uma agenda ou em resposta a alertas.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|||  
|-|-|  
|**Descrição**|**Tópico**|  
|Contém informações sobre como criar trabalhos e atribuir propriedade.|[Criar trabalhos](create-jobs.md)|  
|Contém informações sobre como organizar trabalhos em categorias.|[organizar trabalhos](organize-jobs.md)|  
|Contém informações sobre os diferentes tipos de etapas de trabalho que podem ser criadas e como gerenciá-las.|[Gerenciar etapas de trabalho](manage-job-steps.md)|  
|Contém informações sobre como definir o início e a frequência da execução de trabalhos.|[Criar e anexar agendas para trabalhos](create-and-attach-schedules-to-jobs.md)|  
|Contém informações sobre como executar trabalhos manualmente (sem uma agenda).|[Executar Trabalhos](run-jobs.md)|  
|Contém informações sobre como configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para responder a trabalhos. Por exemplo, você pode configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para notificar administradores quando os trabalhos forem concluídos.|[Especificar respostas de trabalho](specify-job-responses.md)|  
|Contém informações sobre como exibir trabalhos existentes, seu histórico quando executado, e como modificá-los.|[Exibir ou modificar trabalhos](view-or-modify-jobs.md)|  
|Contém informações sobre como excluir trabalhos.|[excluir trabalhos](delete-jobs.md)|  
  
## <a name="see-also"></a>Consulte Também  
 [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md)  
  
  
