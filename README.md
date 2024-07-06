
```javascript

describe('2024-07-06 TaeHwan🔥', () => {
  let app: INestApplication;

  const expectedData = {
    stacks: {
      Language: ['Javascript', 'Typescript', 'Java'],
      Nodejs: ['Express.js', 'Nest.js'],
      DB: ['MySQL', 'mongoDB', 'redis', 'postgreSQL', 'mariaDB'],
      ORM: ['Sequelize', 'TypeORM', 'mongoose'],
      collaborationTools: ['github', 'notion', 'slack', 'figma'],
      cloud: ['AWS'],
    },
    studying: {
      Concepts: ['Clean Architecture'],
      AdvancedTopics: ['Microservices', 'DDD', 'SOLID'],
      Methodologies: ['TDD', 'DevOps'],
    },
    interested: [
      'Large-scale Service Architecture',
      'Agile',
      'Performance Improvement',
      'Refactoring',
    ],
  };

  beforeEach(async () => {
    const moduleFixture: TestingModule = await Test.createTestingModule({
      controllers: [AppController],
    }).compile();

    app = moduleFixture.createNestApplication();
    await app.init();
  });

  afterAll(async () => {
    await app.close();
  });

  it('should return correct data', async () => {
    const response = await request(app.getHttpServer()).get(
      '/antaehwan/stacks',
    );

    expect(response.status).toBe(200);
    expect(response.body).toEqual(expectedData);
  });
});




```
