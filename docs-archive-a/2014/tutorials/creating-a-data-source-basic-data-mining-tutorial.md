---
title: Criando uma fonte de dados (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572292"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a>Criando uma fonte de dados (Tutorial de mineração de dados básico)
  Uma *fonte de dados* é uma conexão de dados que é salva e gerenciada em seu projeto e implantada em seu banco de dado [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] . A fonte de dados contém os nomes do servidor e o banco de dados em que a sua fonte de dados reside, além das demais propriedades de conexão necessárias.  
  
> [!IMPORTANT]  
>  O nome do banco de dados é [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]. Se você ainda não tiver instalado esse banco de dados, consulte a página bancos de dados de [exemplo do Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .  
  
### <a name="to-create-a-data-source"></a>Para criar uma fonte de dados  
  
1.  Em **Gerenciador de soluções**, clique com o botão direito do mouse na pasta **fontes de dados** e selecione **nova fonte de dados**.  
  
2.  Na página **Bem-vindo ao Assistente de Fonte de Dados** , clique em **Próximo**.  
  
3.  Na página **Selecione como definir a conexão** , clique em **novo** para adicionar uma conexão ao banco de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] dados.  
  
4.  Na lista **provedor** no **Gerenciador de conexões**, selecione **Native OLE DB Nativo\SQL servidor nativo Client 11,0**.  
  
5.  Na caixa **nome do servidor** , digite ou selecione o nome do servidor no qual você instalou o [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .  
  
     Por exemplo, digite **localhost** se o banco de dados estiver hospedado no servidor local.  
  
6.  No log no grupo **de servidores** , selecione **usar autenticação do Windows**.  
  
    > [!IMPORTANT]  
    >  Sempre que possível, os implementadores deverão usar a Autenticação do Windows, já que ela oferece um método de autenticação mais seguro do que a Autenticação do SQL Server. No entanto, a Autenticação do SQL Server é fornecida somente para fins de compatibilidade com versões anteriores. Para obter mais informações sobre métodos de autenticação, consulte [mecanismo de banco de dados configuração – provisionamento de conta](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).  
  
7.  Na lista **selecionar ou inserir nome de banco de dados** , selecione [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] e clique em **OK**.  
  
8.  Clique em **Avançar**.  
  
9. Na página **informações sobre representação** , clique em **usar a conta de serviço**e, em seguida, clique em **Avançar**.  
  
     Na página **concluindo o assistente** , observe que, por padrão, a fonte de dados é chamada Adventure Works DW 2012.  
  
10. Clique em **Concluir**.  
  
     A nova fonte de dados, Adventure Works DW 2012, aparece na pasta **fontes de dados** em Gerenciador de soluções.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
 [Criando uma exibição da fonte de dados &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Tarefa anterior da lição  
 [Criando um projeto de Analysis Services &#40;o tutorial de mineração de dados básico&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Criar uma fonte de dados &#40;SSAS multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional)   
 [Definindo uma fonte de dados](../analysis-services/lesson-1-2-defining-a-data-source.md)   
 [Definir opções de representação &#40;SSAS – Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
