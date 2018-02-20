# ServerConnectiongRouter  
Название - Сервер-Маршутизатор.
Цель     -  Соедененить разных клиентов в разных сетях в одну децентрализованную сеть.
Описание -  Сервер Маршутизатор для подключения клиента к удаленной машине. Хранит список маршутов, от клиентов, которые 
            ожидают подключение TCP.Ждет подключений от удаленных машин(узлов сети), которые ждут прямого подключения в 
            обход NAT от других клиентов, пределяет их порт  и адресс и сохраняет в своей таблице.
            Так же ждет подключений от клиентов с целью подключиться к ранее регистрировавшийся машины, этот клиент должен
            получить ее маршут   и отсоединится от сервера. После чего подключиться к этой машине.(Серверная чать)
            В тестах произведен тест функциональности com.server.ServerRouter c подключения клиентов и их соединение.
Основные компоненты
            src
              ClientConnectRouter.java  - точка входа в программу, запуск сервера-каталога
              com
                 server
                      ParsingRequest  - простой разбор заголовка от клиента. 
                      RemoteMashine   - класс определяющий структуру подключившегося клиента.
                      SerrverRouter   - реализация логики сервера,ждет запросы, и отправляет ответы с маршутом или ошибки
            test
               com
                  server 
`                     ParsingRequestTest  - тест разбора заголовка запроса
                      ServerRouterTest    - тест работы ServerRouter, с примером подключения клиентов,  и их дальнейшго соеденения.
                                            Реализован примернный набор действий по инициализации подключения на стороне Клиента

версия    - 1.0.1
автор     - Даниил Голаев
дата      - 16.01.2018