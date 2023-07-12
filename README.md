## Fluxograma do código `mediaVelDirVento()`

```mermaid
graph TD

A[vel_vento3s.size() < 12?] -- Sim --> B[vel_vento3s.push_back(speedV(M_S)); <br> dir_vento3s.push_back(dirVento()); <br> cont_first++;]
A -- Não --> C[cont_first == 12?]

B --> cont_firstIs12[cont_first = 0; <br> media_vel_vento = avg(vel_vento3s); <br> media_dir_vento = avg(dir_vento3s);]

C -- Sim --> cont_firstIs12

C -- Não --> D[vel_vento3s.erase(vel_vento3s.begin()); <br> vel_vento3s.push_back(speedV(M_S)); <br> dir_vento3s.erase(dir_vento3s.begin()); <br> dir_vento3s.push_back(dirVento()); <br> amostras1s++;]

D --> amostras1sIs4[amostras1s == 4?]

amostras1sIs4 -- Sim --> updateMedia[media_vel_vento = avg(vel_vento3s); <br> media_dir_vento = avg(dir_vento3s); <br> amostras1s = 0;]

amostras1sIs4 -- Não --> E[cont_periodo_read_an = 0; <br> flag_calculo_anemometro = 0;]

updateMedia --> E

E --> F[Fim]
