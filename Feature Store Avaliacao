-- Feature Store Avaliacao

select t2.idVendedor, 
       ROUND(AVG(vlNota),1) as AVG_AVALIACAO, 
       count(vlNota) as Qtd_Reviews, 
       round(sum(CASE WHEN isnull(vlnota) then 1 else 0 end)/COUNT(*),1) as PCT_PEDIDO_SEM_AVALIACAO,
       round(sum( CASE WHEN t1.vlNota = 0 then 1 else 0 end),1) as Qtd_Reviews_0,
       round(sum( CASE WHEN t1.vlNota = 5 then 1 else 0 end),1) as Qtd_Reviews_5,
       round(sum( CASE WHEN t1.vlNota = 4 then 1 else 0 end),1) as Qtd_Reviews_4,
       round(sum( CASE WHEN t1.vlNota = 3 then 1 else 0 end),1) as Qtd_Reviews_3,
       round(sum( CASE WHEN t1.vlNota = 2 then 1 end),1) as Qtd_Reviews_2,
       round(sum( CASE WHEN t1.vlNota = 1 then 1 else 0 end),1) as Qtd_Reviews_1,
       round(sum( CASE WHEN t1.vlNota = 0 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_0,
       round(sum( CASE WHEN t1.vlNota = 5 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_5,
       round(sum( CASE WHEN t1.vlNota = 4 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_4,
       round(sum( CASE WHEN t1.vlNota = 3 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_3,
       round(sum( CASE WHEN t1.vlNota = 2 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_2,
       round(sum( CASE WHEN t1.vlNota = 1 then 1 else 0 end)/COUNT(*),1) as PCT_Reviews_1,
       round(sum( CASE WHEN t1.vlNota = 0 then 1 else 0 end),1) as Qtd_Pedidos_Sem_Avaliacao
from silver.olist.avaliacao_pedido as t1
left join silver.olist.item_pedido as t2
ON t1.idPedido = t2.idPedido
group by t2.idVendedor;