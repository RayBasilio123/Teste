   +---------------------------------------+
   |          mediaVelDirVento()            |
   +---------------------------------------+
                     |
                     v
   +-----------------+-----------------+
   | vel_vento3s.size() < 12?            |
   +-----------------+-----------------+
                     |
          +----------+-----------+
          |          |           |
          v          |           v
   +-----------------+     +-----------------------+
   |       Verdadeiro      |          Falso              |
   +-----------------+     +-----------------------+
                     |
   +-----------------+     +-----------------------+
   | vel_vento3s.push_back(speedV(M_S));      |
   | dir_vento3s.push_back(dirVento());        |
   | cont_first++;                                 |
   +-----------------+     +-----------------------+
                     |
   +-----------------+-----------------+
   | cont_first == 12?               |
   +-----------------+-----------------+
                     |
          +----------+-----------+
          |          |           |
          v          |           v
   +-----------------+     +-----------------------+
   | cont_first = 0;             | media_vel_vento =          |
   | media_vel_vento =          | avg(vel_vento3s);          |
   | avg(vel_vento3s);          | media_dir_vento =          |
   | media_dir_vento =          | avg(dir_vento3s);          |
   | avg(dir_vento3s);          | cont_first = 0;              |
   +-----------------+     +-----------------------+
                     |
   +-----------------+-----------------+
   | vel_vento3s.erase(vel_vento3s.begin()); |
   | vel_vento3s.push_back(speedV(M_S));        |
   | dir_vento3s.erase(dir_vento3s.begin()); |
   | dir_vento3s.push_back(dirVento());         |
   | amostras1s++;                                 |
   +-----------------+     +-----------------------+
                     |
   +-----------------+-----------------+
   | amostras1s == 4?              |
   +-----------------+-----------------+
                     |
          +----------+-----------+
          |          |           |
          v          |           v
   +-----------------+     +-----------------------+
   | amostras1s = 0;             | media_vel_vento =          |
   | media_vel_vento =          | avg(vel_vento3s);          |
   | avg(vel_vento3s);          | media_dir_vento =          |
   | media_dir_vento =          | avg(dir_vento3s);          |
   | avg(dir_vento3s);          | amostras1s = 0;              |
   +-----------------+     +-----------------------+
                     |
   +-----------------+-----------------+
   | cont_periodo_read_an = 0;        |
   | flag_calculo_anemometro = 0; |
   +-----------------+-----------------+
                     |
   +-----------------+-----------------+
   |               Fim                           |
   +-----------------+-----------------+
